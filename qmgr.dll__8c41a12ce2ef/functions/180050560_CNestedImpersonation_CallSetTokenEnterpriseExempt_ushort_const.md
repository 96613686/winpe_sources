# CNestedImpersonation::CallSetTokenEnterpriseExempt(ushort const *)

- ea: `0x180050560`
- end: `0x180050796`
- name: `?CallSetTokenEnterpriseExempt@CNestedImpersonation@@QEAAXPEBG@Z`
- size: `566`
- prototype: `void __fastcall(CNestedImpersonation *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800507a0`
- `0x1800ed0a0`

## callees

- `0x18000e370`
- `0x180014310`
- `0x1800377b8`
- `0x180050560`
- `0x1800a1114`
- `0x1800f6ee8`
- `0x1800f9948`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18005063b`
- `ntdll!RtlAdjustPrivilege` at `0x1800506d5`
- `ntdll!RtlAdjustPrivilege` at `0x18005063b`
- `ntdll!RtlAdjustPrivilege` at `0x1800506d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005071d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005071d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005073b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005073b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800505cc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800505cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNestedImpersonation::CallSetTokenEnterpriseExempt(
        CNestedImpersonation *this,
        const unsigned __int16 *a2)
{
  unsigned int LastError; // ecx
  NTSTATUS v4; // eax
  int v5; // ecx
  HANDLE *v6; // rbx
  NTSTATUS v7; // eax
  int v8; // ecx
  NTSTATUS v9; // eax
  int v10; // ecx
  unsigned int v11; // ecx
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v13; // [rsp+28h] [rbp-58h]
  unsigned int v14; // [rsp+38h] [rbp-48h]
  int v15; // [rsp+3Ch] [rbp-44h]
  int v16; // [rsp+40h] [rbp-40h]
  CNestedImpersonation *OldValue; // [rsp+A0h] [rbp+20h] BYREF
  HANDLE *v18; // [rsp+A8h] [rbp+28h] BYREF

  OldValue = this;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, a2);
  if ( a2 && *a2 )
  {
    CopyThreadToken(&v18);
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v13 = 0;
      pExceptionObject = &ComError::`vftable';
      v14 = LastError;
      v15 = 584;
      v16 = 1;
      throw (ComError *)&pExceptionObject;
    }
    LOBYTE(OldValue) = 0;
    v4 = RtlAdjustPrivilege(7u, 1u, 0, (PBOOLEAN)&OldValue);
    v5 = NtStatusToHResult(v4);
    if ( v5 < 0 )
    {
      v13 = 0;
      pExceptionObject = &ComError::`vftable';
      v14 = v5;
      v15 = 588;
      v16 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v6 = v18;
    v7 = SrpSetTokenEnterpriseExempt(*v18);
    v8 = NtStatusToHResult(v7);
    if ( v8 < 0 )
    {
      v13 = 0;
      pExceptionObject = &ComError::`vftable';
      v14 = v8;
      v15 = 590;
      v16 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v9 = RtlAdjustPrivilege(7u, (BOOLEAN)OldValue, 0, (PBOOLEAN)&OldValue);
    v10 = NtStatusToHResult(v9);
    if ( v10 < 0 )
    {
      v13 = 0;
      pExceptionObject = &ComError::`vftable';
      v14 = v10;
      v15 = 593;
      v16 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( !SetThreadToken(0, *v6) )
    {
      if ( (int)GetLastError() > 0 )
        v11 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v11 = GetLastError();
      v13 = 0;
      pExceptionObject = &ComError::`vftable';
      v14 = v11;
      v15 = 597;
      v16 = 1;
      throw (ComError *)&pExceptionObject;
    }
    TokenHandle::Decrement((TokenHandle *)&v18);
  }
}

```

## disassembly

```asm
0x180050560  mov     [rsp-18h+arg_10], rbx
0x180050565  mov     [rsp-18h+OldValue], rcx
0x18005056a  push    rbp
0x18005056b  push    rsi
0x18005056c  push    rdi
0x18005056d  mov     rbp, rsp
0x180050570  sub     rsp, 80h
0x180050577  mov     rbx, rdx
0x18005057a  lea     rax, WPP_GLOBAL_Control
0x180050581  mov     esi, 1
0x180050586  mov     rcx, cs:WPP_GLOBAL_Control
0x18005058d  cmp     rcx, rax
0x180050590  jz      short loc_1800505AE
0x180050592  test    [rcx+1Ch], sil
0x180050596  jz      short loc_1800505AE
0x180050598  lea     edx, [rsi+19h]
0x18005059b  mov     r9, rbx
0x18005059e  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x1800505a5  mov     rcx, [rcx+10h]
0x1800505a9  call    WPP_SF_S
0x1800505ae  xor     edi, edi
0x1800505b0  test    rbx, rbx
0x1800505b3  jz      loc_180050783
0x1800505b9  cmp     [rbx], di
0x1800505bc  jz      loc_180050783
0x1800505c2  lea     rcx, [rbp+arg_8]
0x1800505c6  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x1800505cb  nop
0x1800505cc  call    cs:__imp_RevertToSelf
0x1800505d2  test    eax, eax
0x1800505d4  jnz     short loc_180050629
0x1800505d6  call    cs:__imp_GetLastError
0x1800505dc  test    eax, eax
0x1800505de  jg      short loc_1800505EA
0x1800505e0  call    cs:__imp_GetLastError
0x1800505e6  mov     ecx, eax
0x1800505e8  jmp     short loc_1800505F9
0x1800505ea  call    cs:__imp_GetLastError
0x1800505f0  movzx   ecx, ax
0x1800505f3  or      ecx, 80070000h
0x1800505f9  xorps   xmm0, xmm0
0x1800505fc  movups  [rbp+var_58], xmm0
0x180050600  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180050607  mov     [rbp+pExceptionObject], rax
0x18005060b  mov     [rbp+var_48], ecx
0x18005060e  mov     [rbp+var_44], 248h
0x180050615  mov     [rbp+var_40], esi
0x180050618  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005061f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180050623  call    _CxxThrowException_0
0x180050629  mov     byte ptr [rbp+OldValue], dil
0x18005062d  lea     r9, [rbp+OldValue]; OldValue
0x180050631  xor     r8d, r8d; ForThread
0x180050634  mov     dl, sil; NewValue
0x180050637  lea     ecx, [r8+7]; Privilege
0x18005063b  call    cs:__imp_RtlAdjustPrivilege
0x180050641  mov     ecx, eax; Status
0x180050643  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x180050648  mov     ecx, eax
0x18005064a  test    eax, eax
0x18005064c  jns     short loc_18005067E
0x18005064e  xorps   xmm0, xmm0
0x180050651  movups  [rbp+var_58], xmm0
0x180050655  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005065c  mov     [rbp+pExceptionObject], rax
0x180050660  mov     [rbp+var_48], ecx
0x180050663  mov     [rbp+var_44], 24Ch
0x18005066a  mov     [rbp+var_40], esi
0x18005066d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180050674  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180050678  call    _CxxThrowException_0
0x18005067e  mov     rbx, [rbp+arg_8]
0x180050682  mov     rcx, [rbx]; TokenHandle
0x180050685  call    SrpSetTokenEnterpriseExempt
0x18005068a  mov     ecx, eax; Status
0x18005068c  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x180050691  mov     ecx, eax
0x180050693  test    eax, eax
0x180050695  jns     short loc_1800506C7
0x180050697  xorps   xmm0, xmm0
0x18005069a  movups  [rbp+var_58], xmm0
0x18005069e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800506a5  mov     [rbp+pExceptionObject], rax
0x1800506a9  mov     [rbp+var_48], ecx
0x1800506ac  mov     [rbp+var_44], 24Eh
0x1800506b3  mov     [rbp+var_40], esi
0x1800506b6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800506bd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800506c1  call    _CxxThrowException_0
0x1800506c7  lea     r9, [rbp+OldValue]; OldValue
0x1800506cb  xor     r8d, r8d; ForThread
0x1800506ce  mov     dl, byte ptr [rbp+OldValue]; NewValue
0x1800506d1  lea     ecx, [r8+7]; Privilege
0x1800506d5  call    cs:__imp_RtlAdjustPrivilege
0x1800506db  mov     ecx, eax; Status
0x1800506dd  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x1800506e2  mov     ecx, eax
0x1800506e4  test    eax, eax
0x1800506e6  jns     short loc_180050718
0x1800506e8  xorps   xmm0, xmm0
0x1800506eb  movups  [rbp+var_58], xmm0
0x1800506ef  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800506f6  mov     [rbp+pExceptionObject], rax
0x1800506fa  mov     [rbp+var_48], ecx
0x1800506fd  mov     [rbp+var_44], 251h
0x180050704  mov     [rbp+var_40], esi
0x180050707  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005070e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180050712  call    _CxxThrowException_0
0x180050718  mov     rdx, [rbx]; Token
0x18005071b  xor     ecx, ecx; Thread
0x18005071d  call    cs:__imp_SetThreadToken
0x180050723  test    eax, eax
0x180050725  jnz     short loc_18005077A
0x180050727  call    cs:__imp_GetLastError
0x18005072d  test    eax, eax
0x18005072f  jg      short loc_18005073B
0x180050731  call    cs:__imp_GetLastError
0x180050737  mov     ecx, eax
0x180050739  jmp     short loc_18005074A
0x18005073b  call    cs:__imp_GetLastError
0x180050741  movzx   ecx, ax
0x180050744  or      ecx, 80070000h
0x18005074a  xorps   xmm0, xmm0
0x18005074d  movups  [rbp+var_58], xmm0
0x180050751  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180050758  mov     [rbp+pExceptionObject], rax
0x18005075c  mov     [rbp+var_48], ecx
0x18005075f  mov     [rbp+var_44], 255h
0x180050766  mov     [rbp+var_40], esi
0x180050769  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180050770  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180050774  call    _CxxThrowException_0
0x18005077a  lea     rcx, [rbp+arg_8]; this
0x18005077e  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x180050783  mov     rbx, [rsp+80h+arg_10]
0x18005078b  add     rsp, 80h
0x180050792  pop     rdi
0x180050793  pop     rsi
0x180050794  pop     rbp
0x180050795  retn
```
