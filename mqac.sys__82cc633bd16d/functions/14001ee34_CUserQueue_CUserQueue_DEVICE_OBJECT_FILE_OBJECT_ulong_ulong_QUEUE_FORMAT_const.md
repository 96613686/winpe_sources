# CUserQueue::CUserQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,ulong,ulong,QUEUE_FORMAT const *)

- ea: `0x14001ee34`
- end: `0x14001eed5`
- name: `??0CUserQueue@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@KKPEBUQUEUE_FORMAT@@@Z`
- size: `161`
- prototype: `CUserQueue *(CUserQueue *__hidden this, struct _DEVICE_OBJECT *, struct _FILE_OBJECT *, unsigned int, unsigned int, const struct QUEUE_FORMAT *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001b5a8`
- `0x14001c530`

## callees

- `0x14000d8a0`
- `0x14001ee34`

## import_xrefs

- `ntoskrnl!IoSetShareAccess` at `0x14001eebc`
- `ntoskrnl!IoSetShareAccess` at `0x14001eebc`

## pseudocode

```c
CUserQueue *__fastcall CUserQueue::CUserQueue(
        CUserQueue *this,
        struct _DEVICE_OBJECT *a2,
        struct _FILE_OBJECT *a3,
        ACCESS_MASK a4,
        ULONG DesiredShareAccess,
        const struct QUEUE_FORMAT *a6)
{
  _WORD *v6; // rdi

  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 3) = (char *)this + 16;
  v6 = (_WORD *)((char *)this + 88);
  *((_QWORD *)this + 2) = (char *)this + 16;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 6) = (char *)this + 40;
  *((_QWORD *)this + 5) = (char *)this + 40;
  *((_QWORD *)this + 8) = a2;
  *(_QWORD *)this = &CUserQueue::`vftable';
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  *(_OWORD *)((char *)this + 88) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  if ( !ACpDupQueueFormat(a6, (CUserQueue *)((char *)this + 88)) )
    *v6 = 0;
  IoSetShareAccess(a4, DesiredShareAccess, a3, (PSHARE_ACCESS)((char *)this + 120));
  return this;
}

```

## disassembly

```asm
0x14001ee34  push    rbx
0x14001ee36  push    rbp
0x14001ee37  push    rsi
0x14001ee38  push    rdi
0x14001ee39  sub     rsp, 28h
0x14001ee3d  mov     dword ptr [rcx+8], 1
0x14001ee44  lea     rax, [rcx+10h]
0x14001ee48  mov     [rax+8], rax
0x14001ee4c  lea     rdi, [rcx+58h]
0x14001ee50  mov     [rax], rax
0x14001ee53  xorps   xmm0, xmm0
0x14001ee56  mov     qword ptr [rcx+20h], 0
0x14001ee5e  lea     rax, [rcx+28h]
0x14001ee62  mov     [rax+8], rax
0x14001ee66  mov     rbx, rcx
0x14001ee69  mov     [rax], rax
0x14001ee6c  mov     esi, r9d
0x14001ee6f  mov     [rcx+40h], rdx
0x14001ee73  lea     rax, ??_7CUserQueue@@6B@; const CUserQueue::`vftable'
0x14001ee7a  mov     [rcx], rax
0x14001ee7d  mov     rdx, rdi; struct QUEUE_FORMAT *
0x14001ee80  mov     dword ptr [rcx+38h], 0
0x14001ee87  lea     rax, [rcx+48h]
0x14001ee8b  mov     rcx, [rsp+48h+arg_28]; struct QUEUE_FORMAT *
0x14001ee90  mov     rbp, r8
0x14001ee93  mov     [rax+8], rax
0x14001ee97  mov     [rax], rax
0x14001ee9a  movups  xmmword ptr [rdi], xmm0
0x14001ee9d  movups  xmmword ptr [rdi+10h], xmm0
0x14001eea1  call    ?ACpDupQueueFormat@@YA_NAEBUQUEUE_FORMAT@@AEAU1@@Z; ACpDupQueueFormat(QUEUE_FORMAT const &,QUEUE_FORMAT &)
0x14001eea6  test    al, al
0x14001eea8  jnz     short loc_14001EEAF
0x14001eeaa  mov     word ptr [rdi], 0
0x14001eeaf  mov     edx, [rsp+48h+DesiredShareAccess]; DesiredShareAccess
0x14001eeb3  lea     r9, [rbx+78h]; ShareAccess
0x14001eeb7  mov     r8, rbp; FileObject
0x14001eeba  mov     ecx, esi; DesiredAccess
0x14001eebc  call    cs:__imp_IoSetShareAccess
0x14001eec3  nop     dword ptr [rax+rax+00h]
0x14001eec8  mov     rax, rbx
0x14001eecb  add     rsp, 28h
0x14001eecf  pop     rdi
0x14001eed0  pop     rsi
0x14001eed1  pop     rbp
0x14001eed2  pop     rbx
0x14001eed3  retn
```
