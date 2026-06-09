# I_GenerateUUIDValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001cf50`
- end: `0x18001cfe5`
- name: `?I_GenerateUUIDValue@@YAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `149`
- prototype: `RPC_STATUS __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180013b14`
- `0x18001466c`

## callees

- `0x1800085dc`
- `0x180015300`
- `0x180016090`
- `0x18001c7b8`
- `0x18001cf50`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001cf75`
- `RPCRT4!UuidCreate` at `0x18001cf75`
- `RPCRT4!UuidToStringW` at `0x18001cf92`
- `RPCRT4!UuidToStringW` at `0x18001cf92`

## pseudocode

```c
RPC_STATUS __fastcall I_GenerateUUIDValue(__int64 a1)
{
  RPC_STATUS result; // eax
  __int64 v3; // rax
  __int64 v4; // rcx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-38h] BYREF
  RPC_WSTR *p_StringUuid; // [rsp+28h] [rbp-30h] BYREF
  __int16 v7; // [rsp+30h] [rbp-28h]
  UUID Uuid; // [rsp+38h] [rbp-20h] BYREF

  Uuid = 0;
  result = UuidCreate(&Uuid);
  if ( !result )
  {
    StringUuid = 0;
    result = UuidToStringW(&Uuid, &StringUuid);
    if ( !result )
    {
      p_StringUuid = &StringUuid;
      v7 = 256;
      v3 = std::_WChar_traits<unsigned short>::length(StringUuid);
      std::wstring::_Assign<unsigned short>(a1, v4, v3);
      wil::details::ScopeExitFnGuard__lambda_6496965529bccc85f94e6b07489da901___::operator()(&p_StringUuid);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cf50  push    rbx
0x18001cf52  sub     rsp, 50h
0x18001cf56  mov     rax, cs:__security_cookie
0x18001cf5d  xor     rax, rsp
0x18001cf60  mov     [rsp+58h+var_10], rax
0x18001cf65  mov     rbx, rcx
0x18001cf68  xorps   xmm0, xmm0
0x18001cf6b  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x18001cf70  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18001cf75  call    cs:__imp_UuidCreate
0x18001cf7b  test    eax, eax
0x18001cf7d  jnz     short loc_18001CFD2
0x18001cf7f  mov     [rsp+58h+StringUuid], 0
0x18001cf88  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x18001cf8d  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18001cf92  call    cs:__imp_UuidToStringW
0x18001cf98  test    eax, eax
0x18001cf9a  jnz     short loc_18001CFD2
0x18001cf9c  lea     rax, [rsp+58h+StringUuid]
0x18001cfa1  mov     [rsp+58h+var_30], rax
0x18001cfa6  mov     [rsp+58h+var_28], 100h
0x18001cfad  mov     rcx, [rsp+58h+StringUuid]
0x18001cfb2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001cfb7  mov     r8, rax
0x18001cfba  mov     rdx, rcx
0x18001cfbd  mov     rcx, rbx
0x18001cfc0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001cfc5  nop
0x18001cfc6  lea     rcx, [rsp+58h+var_30]
0x18001cfcb  call    wil__details__ScopeExitFnGuard__lambda_6496965529bccc85f94e6b07489da901_____operator__
0x18001cfd0  xor     eax, eax
0x18001cfd2  mov     rcx, [rsp+58h+var_10]
0x18001cfd7  xor     rcx, rsp; StackCookie
0x18001cfda  call    __security_check_cookie
0x18001cfdf  add     rsp, 50h
0x18001cfe3  pop     rbx
0x18001cfe4  retn
```
