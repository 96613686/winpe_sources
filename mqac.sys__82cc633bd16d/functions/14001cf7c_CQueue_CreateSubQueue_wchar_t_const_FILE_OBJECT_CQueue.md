# CQueue::CreateSubQueue(wchar_t const *,_FILE_OBJECT *,CQueue * *)

- ea: `0x14001cf7c`
- end: `0x14001d05a`
- name: `?CreateSubQueue@CQueue@@QEAAJPEB_WPEAU_FILE_OBJECT@@PEAPEAV1@@Z`
- size: `222`
- prototype: `int(CQueue *__hidden this, const wchar_t *, struct _FILE_OBJECT *, struct CQueue **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140004314`
- `0x140007e3c`

## callees

- `0x140001128`
- `0x14000533c`
- `0x140012754`
- `0x14001cf7c`

## pseudocode

```c
__int64 __fastcall CQueue::CreateSubQueue(CQueue *this, const wchar_t *a2, struct _FILE_OBJECT *a3, struct CQueue **a4)
{
  struct _DEVICE_OBJECT *v7; // rcx
  __int64 result; // rax
  struct CQueue *FsContext; // rbx
  CQueue *v10; // rax
  CQueue **v11; // rdx
  _QWORD v12[2]; // [rsp+30h] [rbp-29h] BYREF
  __int128 v13; // [rsp+40h] [rbp-19h]
  _OWORD v14[3]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v15; // [rsp+80h] [rbp+27h]

  v12[0] = 0;
  v15 = 0;
  v12[1] = a2;
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 8);
  LOWORD(v12[0]) = 1288;
  v14[0] = 0;
  v14[1] = (unsigned __int64)v12;
  v14[2] = 0;
  LODWORD(v14[0]) = 1;
  v13 = 0;
  result = ACCreateQueue(v7, a3, (const struct CACCreateQueueParameters *)v14, 1, 0);
  if ( (int)result >= 0 )
  {
    FsContext = (struct CQueue *)a3->FsContext;
    *((_QWORD *)FsContext + 47) = this;
    v10 = (CQueue *)operator new(0x18u, 0x100u, 0x4341514Du, LowPoolPriority);
    if ( v10 )
    {
      *((_QWORD *)v10 + 2) = FsContext;
      v11 = (CQueue **)*((_QWORD *)this + 46);
      if ( *v11 != (CQueue *)((char *)this + 360) )
        __fastfail(3u);
      *(_QWORD *)v10 = (char *)this + 360;
      *((_QWORD *)v10 + 1) = v11;
      *v11 = v10;
      *((_QWORD *)this + 46) = v10;
      result = 0;
      *a4 = FsContext;
    }
    else
    {
      CBaseObject::Release(FsContext);
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001cf7c  push    rbp
0x14001cf7e  push    rbx
0x14001cf7f  push    rsi
0x14001cf80  push    rdi
0x14001cf81  lea     rbp, [rsp-3Fh]
0x14001cf86  sub     rsp, 98h
0x14001cf8d  xorps   xmm0, xmm0
0x14001cf90  mov     [rsp+0B0h+var_90], 0; int
0x14001cf98  xor     eax, eax
0x14001cf9a  mov     rbx, r8
0x14001cf9d  movups  [rbp+57h+var_80], xmm0
0x14001cfa1  mov     rsi, r9
0x14001cfa4  mov     [rbp+57h+var_30], rax
0x14001cfa8  mov     rdi, rcx
0x14001cfab  mov     qword ptr [rbp+57h+var_80+8], rdx
0x14001cfaf  mov     rcx, [rcx+40h]; struct _DEVICE_OBJECT *
0x14001cfb3  lea     r9d, [rax+1]; int
0x14001cfb7  lea     rax, [rbp+57h+var_80]
0x14001cfbb  mov     word ptr [rbp+57h+var_80], 508h
0x14001cfc1  movups  [rbp+57h+var_60], xmm0
0x14001cfc5  lea     r8, [rbp+57h+var_60]; struct CACCreateQueueParameters *
0x14001cfc9  mov     rdx, rbx; struct _FILE_OBJECT *
0x14001cfcc  movups  [rbp+57h+var_50], xmm0
0x14001cfd0  mov     qword ptr [rbp+57h+var_50], rax
0x14001cfd4  movups  [rbp+57h+var_40], xmm0
0x14001cfd8  mov     dword ptr [rbp+57h+var_60], r9d
0x14001cfdc  movups  [rbp+57h+var_70], xmm0
0x14001cfe0  call    ?ACCreateQueue@@YAJPEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@PEBVCACCreateQueueParameters@@HH@Z; ACCreateQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,CACCreateQueueParameters const *,int,int)
0x14001cfe5  test    eax, eax
0x14001cfe7  js      short loc_14001D04D
0x14001cfe9  mov     rbx, [rbx+18h]
0x14001cfed  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14001cff0  mov     edx, 100h; unsigned __int64
0x14001cff5  mov     r8d, 4341514Dh; unsigned int
0x14001cffb  lea     ecx, [r9+18h]; unsigned __int64
0x14001cfff  mov     [rbx+178h], rdi
0x14001d006  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14001d00b  test    rax, rax
0x14001d00e  jz      short loc_14001D040
0x14001d010  lea     rcx, [rdi+168h]
0x14001d017  mov     [rax+10h], rbx
0x14001d01b  mov     rdx, [rcx+8]
0x14001d01f  cmp     [rdx], rcx
0x14001d022  jz      short loc_14001D02B
0x14001d024  mov     ecx, 3
0x14001d029  int     29h; Win8: RtlFailFast(ecx)
0x14001d02b  mov     [rax], rcx
0x14001d02e  mov     [rax+8], rdx
0x14001d032  mov     [rdx], rax
0x14001d035  mov     [rcx+8], rax
0x14001d039  xor     eax, eax
0x14001d03b  mov     [rsi], rbx
0x14001d03e  jmp     short loc_14001D04D
0x14001d040  mov     rcx, rbx; this
0x14001d043  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001d048  mov     eax, 0C000009Ah
0x14001d04d  add     rsp, 98h
0x14001d054  pop     rdi
0x14001d055  pop     rsi
0x14001d056  pop     rbx
0x14001d057  pop     rbp
0x14001d058  retn
```
