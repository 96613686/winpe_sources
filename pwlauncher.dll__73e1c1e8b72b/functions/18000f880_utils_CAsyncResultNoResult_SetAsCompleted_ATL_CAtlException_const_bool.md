# utils::CAsyncResultNoResult::SetAsCompleted(ATL::CAtlException const &,bool)

- ea: `0x18000f880`
- end: `0x18000fa10`
- name: `?SetAsCompleted@CAsyncResultNoResult@utils@@UEAAXAEBVCAtlException@ATL@@_N@Z`
- size: `400`
- prototype: `void __fastcall(utils::CAsyncResultNoResult *this, const struct ATL::CAtlException *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000d390`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x180008b30`
- `0x180009878`
- `0x18000f754`
- `0x18000f880`
- `0x180011010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f8ad`
- `KERNEL32!SetEvent` at `0x18000f8ad`
- `KERNEL32!GetLastError` at `0x18000f920`
- `KERNEL32!GetLastError` at `0x18000f920`

## pseudocode

```c
void __fastcall utils::CAsyncResultNoResult::SetAsCompleted(
        utils::CAsyncResultNoResult *this,
        const struct ATL::CAtlException *a2,
        unsigned __int8 a3)
{
  void (__fastcall ***v4)(_QWORD, _QWORD *); // r8
  __int64 v5; // rdx
  void (__fastcall **v6)(_QWORD, _QWORD *); // r9
  __int64 v7; // r10
  signed __int32 v8; // eax
  signed int LastError; // eax
  unsigned int v10; // edx
  int v11; // r8d
  int v12; // ebx
  int v13; // [rsp+28h] [rbp-38h]
  _QWORD v14[2]; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v15[2]; // [rsp+40h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+80h] [rbp+20h] BYREF

  *((_DWORD *)this + 13) = *(_DWORD *)a2;
  if ( _InterlockedExchange((volatile __int32 *)this + 12, (a3 ^ 1) + 1) )
  {
    utils::CInvalidOperationException::CInvalidOperationException((utils::CInvalidOperationException *)&pExceptionObject);
    v12 = pExceptionObject;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_d91e401e6ac0313360b28a264a83eb95_Traceguids,
        (unsigned int)"CInvalidOperationException()",
        pExceptionObject);
    pExceptionObject = v12;
    throw (utils::CInvalidOperationException *)&pExceptionObject;
  }
  if ( !SetEvent(*((HANDLE *)this + 5)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    else
      v10 = LastError;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v10);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = v11;
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_d91e401e6ac0313360b28a264a83eb95_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\casyncresultnoresult.cpp",
        109,
        v13);
    }
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v4 = (void (__fastcall ***)(_QWORD, _QWORD *))*((_QWORD *)this + 3);
  if ( v4 )
  {
    v15[0] = 0;
    v5 = *((_QWORD *)this + 2);
    if ( !v5 )
    {
LABEL_18:
      std::tr1::bad_weak_ptr::bad_weak_ptr((std::tr1::bad_weak_ptr *)v15, (const char *)v5);
      throw (std::tr1::bad_weak_ptr *)v15;
    }
    v6 = *v4;
    v7 = *((_QWORD *)this + 1);
    do
    {
      v8 = *(_DWORD *)(v5 + 8);
      if ( !v8 )
        goto LABEL_18;
    }
    while ( v8 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v8 + 1, v8) );
    v14[0] = v7;
    v14[1] = v5;
    v15[0] = 0;
    (*v6)(v4, v14);
  }
}

```

## disassembly

```asm
0x18000f880  mov     [rsp-8+arg_8], rbx
0x18000f885  push    rbp
0x18000f886  mov     rbp, rsp
0x18000f889  sub     rsp, 60h
0x18000f88d  mov     rbx, rcx
0x18000f890  mov     eax, [rdx]
0x18000f892  mov     [rcx+34h], eax
0x18000f895  movzx   eax, r8b
0x18000f899  xor     eax, 1
0x18000f89c  inc     eax
0x18000f89e  xchg    eax, [rcx+30h]
0x18000f8a1  test    eax, eax
0x18000f8a3  jnz     loc_18000F9B7
0x18000f8a9  mov     rcx, [rcx+28h]; hEvent
0x18000f8ad  call    cs:__imp_SetEvent
0x18000f8b3  test    eax, eax
0x18000f8b5  jz      short loc_18000F920
0x18000f8b7  mov     r8, [rbx+18h]
0x18000f8bb  test    r8, r8
0x18000f8be  jz      short loc_18000F915
0x18000f8c0  xorps   xmm0, xmm0
0x18000f8c3  movdqu  [rbp+var_20], xmm0
0x18000f8c8  mov     rdx, [rbx+10h]; char *
0x18000f8cc  test    rdx, rdx
0x18000f8cf  jz      loc_18000F99D
0x18000f8d5  mov     r9, [r8]
0x18000f8d8  mov     r10, [rbx+8]
0x18000f8dc  jmp     short loc_18000F8E8
0x18000f8de  lea     ecx, [rax+1]
0x18000f8e1  lock cmpxchg [rdx+8], ecx
0x18000f8e6  jz      short loc_18000F8F5
0x18000f8e8  mov     eax, [rdx+8]
0x18000f8eb  test    eax, eax
0x18000f8ed  jz      loc_18000F99D
0x18000f8f3  jmp     short loc_18000F8DE
0x18000f8f5  mov     [rbp+var_30], r10
0x18000f8f9  mov     [rbp+var_28], rdx
0x18000f8fd  xorps   xmm0, xmm0
0x18000f900  movdqu  [rbp+var_20], xmm0
0x18000f905  lea     rdx, [rbp+var_30]
0x18000f909  mov     rcx, r8
0x18000f90c  mov     rax, [r9]
0x18000f90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f914  nop
0x18000f915  mov     rbx, [rsp+60h+arg_8]
0x18000f91a  add     rsp, 60h
0x18000f91e  pop     rbp
0x18000f91f  retn
0x18000f920  call    cs:__imp_GetLastError
0x18000f926  mov     r8d, eax
0x18000f929  test    eax, eax
0x18000f92b  jg      short loc_18000F931
0x18000f92d  mov     edx, eax
0x18000f92f  jmp     short loc_18000F93B
0x18000f931  movzx   edx, r8w
0x18000f935  or      edx, 80070000h; int
0x18000f93b  lea     rcx, [rbp+pExceptionObject]; this
0x18000f93f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000f944  lea     rax, WPP_GLOBAL_Control
0x18000f94b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f952  cmp     rcx, rax
0x18000f955  jz      short loc_18000F986
0x18000f957  test    byte ptr [rcx+1Ch], 1
0x18000f95b  jz      short loc_18000F986
0x18000f95d  mov     edx, 0Eh
0x18000f962  mov     [rsp+60h+var_38], r8d
0x18000f967  mov     [rsp+60h+var_40], 6Dh ; 'm'
0x18000f96f  lea     r9, aDriversWdmUsbp_14; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000f976  lea     r8, WPP_d91e401e6ac0313360b28a264a83eb95_Traceguids
0x18000f97d  mov     rcx, [rcx+10h]
0x18000f981  call    WPP_SF_sdD
0x18000f986  mov     eax, [rbp+pExceptionObject]
0x18000f989  mov     [rbp+pExceptionObject], eax
0x18000f98c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000f993  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f997  call    _CxxThrowException_0
0x18000f99d  lea     rcx, [rbp+var_20]; this
0x18000f9a1  call    ??0bad_weak_ptr@tr1@std@@QEAA@PEBD@Z; std::tr1::bad_weak_ptr::bad_weak_ptr(char const *)
0x18000f9a6  lea     rdx, _TI2?AVbad_weak_ptr@tr1@std@@; pThrowInfo
0x18000f9ad  lea     rcx, [rbp+var_20]; pExceptionObject
0x18000f9b1  call    _CxxThrowException_0
0x18000f9b7  lea     rcx, [rbp+pExceptionObject]; this
0x18000f9bb  call    ??0CInvalidOperationException@utils@@QEAA@XZ; utils::CInvalidOperationException::CInvalidOperationException(void)
0x18000f9c0  lea     rax, WPP_GLOBAL_Control
0x18000f9c7  mov     ebx, [rbp+pExceptionObject]
0x18000f9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9d1  cmp     rcx, rax
0x18000f9d4  jz      short loc_18000F9FC
0x18000f9d6  test    byte ptr [rcx+1Ch], 1
0x18000f9da  jz      short loc_18000F9FC
0x18000f9dc  mov     edx, 0Dh
0x18000f9e1  mov     [rsp+60h+var_40], ebx
0x18000f9e5  lea     r9, aCinvalidoperat; "CInvalidOperationException()"
0x18000f9ec  lea     r8, WPP_d91e401e6ac0313360b28a264a83eb95_Traceguids
0x18000f9f3  mov     rcx, [rcx+10h]
0x18000f9f7  call    WPP_SF_sd
0x18000f9fc  mov     [rbp+pExceptionObject], ebx
0x18000f9ff  lea     rdx, _TI2?AVCInvalidOperationException@utils@@; pThrowInfo
0x18000fa06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000fa0a  call    _CxxThrowException_0
```
