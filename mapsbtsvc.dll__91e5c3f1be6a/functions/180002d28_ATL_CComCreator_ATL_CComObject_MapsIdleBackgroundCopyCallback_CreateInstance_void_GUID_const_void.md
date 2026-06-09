# ATL::CComCreator<ATL::CComObject<MapsIdleBackgroundCopyCallback>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002d28`
- end: `0x180002df3`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002d00`

## callees

- `0x18000224c`
- `0x1800029c0`
- `0x180002d28`
- `0x18000303c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<MapsIdleBackgroundCopyCallback>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  void *v6; // rax
  _BYTE *v7; // rbx
  int v8; // edi
  _BYTE *v11; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v6 = operator new(0x40u);
    v7 = (_BYTE *)ATL::CComObject<MapsIdleBackgroundCopyCallback>::CComObject<MapsIdleBackgroundCopyCallback>((__int64)v6);
    v11 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v11;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002d28  mov     [rsp+arg_10], r8
0x180002d2d  mov     [rsp+arg_8], rdx
0x180002d32  mov     [rsp+arg_0], rcx
0x180002d37  push    rbx
0x180002d38  push    rsi
0x180002d39  push    rdi
0x180002d3a  push    r14
0x180002d3c  push    r15
0x180002d3e  sub     rsp, 20h
0x180002d42  mov     rsi, r8
0x180002d45  mov     r14, rdx
0x180002d48  test    r8, r8
0x180002d4b  jnz     short loc_180002D57
0x180002d4d  mov     eax, 80004003h
0x180002d52  jmp     loc_180002DE7
0x180002d57  mov     qword ptr [r8], 0
0x180002d5e  mov     edi, 8007000Eh
0x180002d63  mov     dword ptr [rsp+48h+arg_0], edi
0x180002d67  mov     [rsp+48h+arg_18], 0
0x180002d70  mov     ecx, 40h ; '@'; Size
0x180002d75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d7a  mov     rcx, rax
0x180002d7d  call    ??0?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<MapsIdleBackgroundCopyCallback>::CComObject<MapsIdleBackgroundCopyCallback>(void *)
0x180002d82  mov     rbx, rax
0x180002d85  mov     [rsp+48h+arg_18], rax
0x180002d8a  jmp     short loc_180002D9F
0x180002d8c  mov     rsi, [rsp+48h+arg_10]
0x180002d91  mov     r14, [rsp+48h+arg_8]
0x180002d96  mov     edi, dword ptr [rsp+48h+arg_0]
0x180002d9a  mov     rbx, [rsp+48h+arg_18]
0x180002d9f  test    rbx, rbx
0x180002da2  jz      short loc_180002DE5
0x180002da4  lea     rcx, [rbx+10h]; this
0x180002da8  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002dad  mov     edi, eax
0x180002daf  test    eax, eax
0x180002db1  js      short loc_180002DD1
0x180002db3  mov     byte ptr [rbx+38h], 1
0x180002db7  mov     rax, [rbx]
0x180002dba  mov     r8, rsi
0x180002dbd  mov     rdx, r14
0x180002dc0  mov     rcx, rbx
0x180002dc3  mov     rax, [rax]
0x180002dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcb  mov     edi, eax
0x180002dcd  test    eax, eax
0x180002dcf  jz      short loc_180002DE5
0x180002dd1  mov     rax, [rbx]
0x180002dd4  mov     edx, 1
0x180002dd9  mov     rcx, rbx
0x180002ddc  mov     rax, [rax+38h]
0x180002de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de5  mov     eax, edi
0x180002de7  add     rsp, 20h
0x180002deb  pop     r15
0x180002ded  pop     r14
0x180002def  pop     rdi
0x180002df0  pop     rsi
0x180002df1  pop     rbx
0x180002df2  retn
```
