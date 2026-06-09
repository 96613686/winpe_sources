# PCW_QUERY::Create(void * *,ulong,utl::unique_ptr<_KEVENT,GenericDeleter<_KEVENT,__int64 (void *),&ObfDereferenceObject(void *)>>)

- ea: `0x140009558`
- end: `0x140009616`
- name: `?Create@PCW_QUERY@@SAJPEAPEAXKV?$unique_ptr@U_KEVENT@@U?$GenericDeleter@U_KEVENT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@@@utl@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(PHANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a280`

## callees

- `0x140009558`
- `0x14000ca84`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400095a0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400095a0`
- `ntoskrnl!ObInsertObject` at `0x1400095e8`
- `ntoskrnl!ObInsertObject` at `0x1400095e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400095fe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400095fe`

## pseudocode

```c
__int64 __fastcall PCW_QUERY::Create(PHANDLE Handle, __int64 a2, PVOID *a3, __int64 a4)
{
  int inserted; // ebx
  _QWORD *v7; // rdi
  PVOID v8; // rax
  PVOID Object; // [rsp+78h] [rbp+20h] BYREF

  Object = 0;
  inserted = PcwpCreateObject(&Object, 56, (__int64)a3, a4);
  if ( inserted >= 0 )
  {
    v7 = Object;
    *(_DWORD *)Object = 0;
    v7[1] = 0;
    *((_OWORD *)v7 + 1) = 0;
    v7[4] = PsGetCurrentProcess();
    v8 = *a3;
    *a3 = 0;
    v7[5] = v8;
    *((_DWORD *)v7 + 12) = 0;
    v7[3] = v7 + 2;
    v7[2] = v7 + 2;
    inserted = ObInsertObject(v7, 0, 0xF0003u, 0, 0, Handle);
  }
  if ( *a3 )
    ObfDereferenceObject(*a3);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140009558  push    rbx
0x14000955a  push    rbp
0x14000955b  push    rsi
0x14000955c  push    rdi
0x14000955d  sub     rsp, 38h
0x140009561  mov     rbp, rcx
0x140009564  mov     [rsp+58h+Object], 0
0x14000956d  lea     rcx, [rsp+58h+Object]; void **
0x140009572  mov     edx, 38h ; '8'; unsigned int
0x140009577  mov     rsi, r8
0x14000957a  call    ?PcwpCreateObject@@YAJPEAPEAXK@Z; PcwpCreateObject(void * *,ulong)
0x14000957f  mov     ebx, eax
0x140009581  test    eax, eax
0x140009583  js      short loc_1400095F6
0x140009585  mov     rdi, [rsp+58h+Object]
0x14000958a  xor     eax, eax
0x14000958c  xorps   xmm0, xmm0
0x14000958f  mov     dword ptr [rdi], 0
0x140009595  lea     rbx, [rdi+10h]
0x140009599  mov     [rdi+8], rax
0x14000959d  movups  xmmword ptr [rbx], xmm0
0x1400095a0  call    cs:__imp_PsGetCurrentProcess
0x1400095a7  nop     dword ptr [rax+rax+00h]
0x1400095ac  mov     [rsp+58h+Handle], rbp; Handle
0x1400095b1  xor     r9d, r9d; ObjectPointerBias
0x1400095b4  mov     [rdi+20h], rax
0x1400095b8  xor     edx, edx; PassedAccessState
0x1400095ba  mov     rax, [rsi]
0x1400095bd  mov     r8d, 0F0003h; DesiredAccess
0x1400095c3  mov     qword ptr [rsi], 0
0x1400095ca  mov     rcx, rdi; Object
0x1400095cd  mov     [rdi+28h], rax
0x1400095d1  mov     dword ptr [rdi+30h], 0
0x1400095d8  mov     [rbx+8], rbx
0x1400095dc  mov     [rbx], rbx
0x1400095df  mov     [rsp+58h+NewObject], 0; NewObject
0x1400095e8  call    cs:__imp_ObInsertObject
0x1400095ef  nop     dword ptr [rax+rax+00h]
0x1400095f4  mov     ebx, eax
0x1400095f6  mov     rcx, [rsi]; Object
0x1400095f9  test    rcx, rcx
0x1400095fc  jz      short loc_14000960A
0x1400095fe  call    cs:__imp_ObfDereferenceObject
0x140009605  nop     dword ptr [rax+rax+00h]
0x14000960a  mov     eax, ebx
0x14000960c  add     rsp, 38h
0x140009610  pop     rdi
0x140009611  pop     rsi
0x140009612  pop     rbp
0x140009613  pop     rbx
0x140009614  retn
```
