# PwrshPlugInMediator::VerifyAndStoreExtraInfo(ushort const *,ushort * *)

- ea: `0x180004370`
- end: `0x180004522`
- name: `?VerifyAndStoreExtraInfo@PwrshPlugInMediator@@QEAAXPEBGPEAPEAG@Z`
- size: `434`
- prototype: `void __fastcall(PwrshPlugInMediator *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180003a68`
- `0x180004960`

## callees

- `0x180001098`
- `0x180001318`
- `0x180001dfc`
- `0x180002058`
- `0x180002e80`
- `0x1800042ec`
- `0x180004370`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::VerifyAndStoreExtraInfo(
        PwrshPlugInMediator *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  PlugInException *v9; // rax
  PlugInException *v10; // rax
  PlugInException *v11; // rax
  PlugInException *v12; // rax
  PlugInException *v13; // rax
  PlugInException *v14; // rax
  unsigned __int16 *v15; // [rsp+50h] [rbp+30h] BYREF
  PlugInException *pExceptionObject; // [rsp+58h] [rbp+38h] BYREF

  v15 = (unsigned __int16 *)this;
  if ( !a2 )
  {
    v15 = 0;
    GetFormattedErrorMessage(&v15, 0x805403ED, L"PSVersion", L"InitializationParameters");
    v11 = (PlugInException *)operator new(0x10u);
    pExceptionObject = v11;
    if ( v11 )
      v12 = PlugInException::PlugInException(v11, 0x805403ED, v15);
    else
      v12 = 0;
    pExceptionObject = v12;
    throw (PlugInException **)&pExceptionObject;
  }
  v5 = a2;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
  {
    v15 = 0;
    GetFormattedErrorMessage(&v15, 0x805403EE, L"InitializationParameters");
    v13 = (PlugInException *)operator new(0x10u);
    pExceptionObject = v13;
    if ( v13 )
      v14 = PlugInException::PlugInException(v13, 0x805403EE, v15);
    else
      v14 = 0;
    pExceptionObject = v14;
    throw (PlugInException **)&pExceptionObject;
  }
  if ( a3 )
  {
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v7 + 1, 2u));
    *a3 = v8;
    if ( (int)StringCchCopyNW(v8, v7 + 1, a2, v7) < 0 )
    {
      v15 = 0;
      GetFormattedErrorMessage(&v15, 0x805403EE, L"InitializationParameters");
      v9 = (PlugInException *)operator new(0x10u);
      pExceptionObject = v9;
      if ( v9 )
        v10 = PlugInException::PlugInException(v9, 0x805403EE, v15);
      else
        v10 = 0;
      pExceptionObject = v10;
      throw (PlugInException **)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180004370  mov     [rsp-28h+arg_10], rbx
0x180004375  mov     [rsp-28h+arg_0], rcx
0x18000437a  push    rbp
0x18000437b  push    rsi
0x18000437c  push    rdi
0x18000437d  push    r14
0x18000437f  push    r15
0x180004381  mov     rbp, rsp
0x180004384  sub     rsp, 20h
0x180004388  xor     r15d, r15d
0x18000438b  mov     r14, r8
0x18000438e  mov     rdi, rdx
0x180004391  test    rdx, rdx
0x180004394  jz      loc_18000446F
0x18000439a  mov     edx, 7FFFFFFFh
0x18000439f  mov     rax, rdi
0x1800043a2  mov     ecx, edx
0x1800043a4  cmp     [rax], r15w
0x1800043a8  jz      short loc_1800043B4
0x1800043aa  add     rax, 2
0x1800043ae  sub     rcx, 1
0x1800043b2  jnz     short loc_1800043A4
0x1800043b4  sub     rdx, rcx
0x1800043b7  mov     rax, rcx
0x1800043ba  neg     rax
0x1800043bd  sbb     rsi, rsi
0x1800043c0  and     rsi, rdx
0x1800043c3  test    rcx, rcx
0x1800043c6  jz      loc_1800044CC
0x1800043cc  test    r14, r14
0x1800043cf  jz      short loc_180004408
0x1800043d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800043d8  lea     rbx, [rsi+1]
0x1800043dc  mov     eax, 2
0x1800043e1  mul     rbx
0x1800043e4  cmovb   rax, rcx
0x1800043e8  mov     rcx, rax; unsigned __int64
0x1800043eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800043f0  mov     r9, rsi; unsigned __int64
0x1800043f3  mov     [r14], rax
0x1800043f6  mov     r8, rdi; unsigned __int16 *
0x1800043f9  mov     rdx, rbx; unsigned __int64
0x1800043fc  mov     rcx, rax; unsigned __int16 *
0x1800043ff  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180004404  test    eax, eax
0x180004406  js      short loc_180004419
0x180004408  mov     rbx, [rsp+20h+arg_10]
0x18000440d  add     rsp, 20h
0x180004411  pop     r15
0x180004413  pop     r14
0x180004415  pop     rdi
0x180004416  pop     rsi
0x180004417  pop     rbp
0x180004418  retn
0x180004419  mov     ebx, 805403EEh
0x18000441e  mov     [rbp+arg_0], r15
0x180004422  mov     edx, ebx; unsigned int
0x180004424  lea     r8, aInitialization; "InitializationParameters"
0x18000442b  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18000442f  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180004434  mov     ecx, 10h; Size
0x180004439  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000443e  mov     [rbp+pExceptionObject], rax
0x180004442  test    rax, rax
0x180004445  jz      short loc_180004457
0x180004447  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18000444b  mov     edx, ebx; unsigned int
0x18000444d  mov     rcx, rax; this
0x180004450  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x180004455  jmp     short loc_18000445A
0x180004457  mov     rax, r15
0x18000445a  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x180004461  mov     [rbp+pExceptionObject], rax
0x180004465  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004469  call    _CxxThrowException_0
0x18000446f  mov     ebx, 805403EDh
0x180004474  mov     [rbp+arg_0], r15
0x180004478  mov     edx, ebx; unsigned int
0x18000447a  lea     r9, aInitialization; "InitializationParameters"
0x180004481  lea     r8, aPsversion; "PSVersion"
0x180004488  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18000448c  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180004491  mov     ecx, 10h; Size
0x180004496  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000449b  mov     [rbp+pExceptionObject], rax
0x18000449f  test    rax, rax
0x1800044a2  jz      short loc_1800044B4
0x1800044a4  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x1800044a8  mov     edx, ebx; unsigned int
0x1800044aa  mov     rcx, rax; this
0x1800044ad  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x1800044b2  jmp     short loc_1800044B7
0x1800044b4  mov     rax, r15
0x1800044b7  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x1800044be  mov     [rbp+pExceptionObject], rax
0x1800044c2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800044c6  call    _CxxThrowException_0
0x1800044cc  mov     ebx, 805403EEh
0x1800044d1  mov     [rbp+arg_0], r15
0x1800044d5  mov     edx, ebx; unsigned int
0x1800044d7  lea     r8, aInitialization; "InitializationParameters"
0x1800044de  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x1800044e2  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x1800044e7  mov     ecx, 10h; Size
0x1800044ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044f1  mov     [rbp+pExceptionObject], rax
0x1800044f5  test    rax, rax
0x1800044f8  jz      short loc_18000450A
0x1800044fa  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x1800044fe  mov     edx, ebx; unsigned int
0x180004500  mov     rcx, rax; this
0x180004503  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x180004508  jmp     short loc_18000450D
0x18000450a  mov     rax, r15
0x18000450d  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x180004514  mov     [rbp+pExceptionObject], rax
0x180004518  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000451c  call    _CxxThrowException_0
```
