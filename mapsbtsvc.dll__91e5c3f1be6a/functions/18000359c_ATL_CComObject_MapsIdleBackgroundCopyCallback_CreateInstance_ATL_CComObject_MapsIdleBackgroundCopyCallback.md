# ATL::CComObject<MapsIdleBackgroundCopyCallback>::CreateInstance(ATL::CComObject<MapsIdleBackgroundCopyCallback> * *)

- ea: `0x18000359c`
- end: `0x180003645`
- name: `?CreateInstance@?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@SAJPEAPEAV12@@Z`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x18000224c`
- `0x1800029c0`
- `0x18000303c`
- `0x18000359c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MapsIdleBackgroundCopyCallback>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // rsi
  void *v3; // rax
  int v4; // ebx
  _BYTE *v5; // rdi
  _BYTE *v7; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v4 = -2147024882;
    v3 = operator new(0x40u);
    v5 = (_BYTE *)ATL::CComObject<MapsIdleBackgroundCopyCallback>::CComObject<MapsIdleBackgroundCopyCallback>((__int64)v3);
    v7 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v4 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v4 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v5 + 16));
    if ( v4 < 0 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
      v5 = 0;
    }
    else
    {
      v5[56] = 1;
      v4 = 0;
    }
  }
  *v1 = v5;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000359c  mov     [rsp+arg_18], rbx
0x1800035a1  mov     [rsp+arg_0], rcx
0x1800035a6  push    rsi
0x1800035a7  push    rdi
0x1800035a8  push    r14
0x1800035aa  sub     rsp, 20h
0x1800035ae  mov     rsi, rcx
0x1800035b1  test    rcx, rcx
0x1800035b4  jnz     short loc_1800035BD
0x1800035b6  mov     eax, 80004003h
0x1800035bb  jmp     short loc_180003637
0x1800035bd  mov     qword ptr [rcx], 0
0x1800035c4  mov     ebx, 8007000Eh
0x1800035c9  mov     [rsp+38h+arg_8], ebx
0x1800035cd  mov     [rsp+38h+arg_10], 0
0x1800035d6  mov     ecx, 40h ; '@'; Size
0x1800035db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035e0  mov     rcx, rax
0x1800035e3  call    ??0?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<MapsIdleBackgroundCopyCallback>::CComObject<MapsIdleBackgroundCopyCallback>(void *)
0x1800035e8  mov     rdi, rax
0x1800035eb  mov     [rsp+38h+arg_10], rax
0x1800035f0  jmp     short loc_180003600
0x1800035f2  mov     rsi, [rsp+38h+arg_0]
0x1800035f7  mov     ebx, [rsp+38h+arg_8]
0x1800035fb  mov     rdi, [rsp+38h+arg_10]
0x180003600  test    rdi, rdi
0x180003603  jz      short loc_180003632
0x180003605  lea     rcx, [rdi+10h]; this
0x180003609  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000360e  mov     ebx, eax
0x180003610  test    eax, eax
0x180003612  js      short loc_18000361C
0x180003614  mov     byte ptr [rdi+38h], 1
0x180003618  xor     ebx, ebx
0x18000361a  jmp     short loc_180003632
0x18000361c  mov     rcx, [rdi]
0x18000361f  mov     rax, [rcx+38h]
0x180003623  mov     edx, 1
0x180003628  mov     rcx, rdi
0x18000362b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003630  xor     edi, edi
0x180003632  mov     [rsi], rdi
0x180003635  mov     eax, ebx
0x180003637  mov     rbx, [rsp+38h+arg_18]
0x18000363c  add     rsp, 20h
0x180003640  pop     r14
0x180003642  pop     rdi
0x180003643  pop     rsi
0x180003644  retn
```
