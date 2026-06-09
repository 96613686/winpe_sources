# CRAHelperClass::SetUtilities(INetDiagHelperUtilFactory *)

- ea: `0x18000f010`
- end: `0x18000f175`
- name: `?SetUtilities@CRAHelperClass@@UEAAJPEAUINetDiagHelperUtilFactory@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(CRAHelperClass *__hidden this, struct INetDiagHelperUtilFactory *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000f010`
- `0x180014660`
- `0x18001a5a2`
- `0x18001c010`

## string_xrefs

- `0x18000f11f`: `RemoteAccessibilityIssue`
- `0x18000f0cf`: `@FirewallAPI.dll,-33002`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::SetUtilities(CRAHelperClass *this, struct INetDiagHelperUtilFactory *a2)
{
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  __int64 *v7; // rbx
  __int64 v8; // rcx
  signed int v9; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // rcx
  signed int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  const wchar_t *v19; // [rsp+30h] [rbp-59h] BYREF
  int v20; // [rsp+38h] [rbp-51h]
  const OLECHAR *v21; // [rsp+40h] [rbp-49h]

  memset_0(&v19, 0, 0x90u);
  if ( a2 )
  {
    v7 = (__int64 *)((char *)this + 128);
    v8 = *((_QWORD *)this + 16);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *v7 = 0;
    }
    v9 = ((__int64 (__fastcall *)(struct INetDiagHelperUtilFactory *, GUID *, char *))a2->lpVtbl->CreateUtilityInstance)(
           a2,
           &GUID_91880d0a_a54a_49fd_b232_0064a885c7bf,
           (char *)this + 128);
    v12 = v9;
    if ( v9 >= 0 )
    {
      v13 = *v7;
      v19 = L"rulegroupname";
      v20 = 10;
      v21 = L"@FirewallAPI.dll,-33002";
      v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v13 + 24LL))(v13, &v19);
      if ( *((_DWORD *)this + 26) == 3 )
      {
        v20 = 1;
        LODWORD(v21) = 1;
        v17 = *v7;
        v19 = L"isInfraHost";
        (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v17 + 24LL))(v17, &v19);
        v18 = *v7;
        v19 = L"RemoteAccessibilityIssue";
        LODWORD(v21) = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v18 + 40LL))(v18, &v19);
      }
      if ( v14 < 0 )
        CEventLogger::LogError(
          v16,
          v15,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x669u,
          L"CRAHelperClass::SetUtilities",
          v14);
    }
    else
    {
      CEventLogger::LogError(
        v11,
        v10,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x649u,
        L"CRAHelperClass::SetUtilities",
        v9);
    }
    return v12;
  }
  else
  {
    CEventLogger::LogError(
      v5,
      v4,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x641u,
      L"CRAHelperClass::SetUtilities",
      0x80070057);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000f010  push    rbp
0x18000f012  push    rbx
0x18000f013  push    rsi
0x18000f014  push    rdi
0x18000f015  lea     rbp, [rsp-3Fh]
0x18000f01a  sub     rsp, 0C8h
0x18000f021  mov     rdi, rdx
0x18000f024  mov     rsi, rcx
0x18000f027  xor     edx, edx; Val
0x18000f029  lea     rcx, [rbp+57h+var_B0]; void *
0x18000f02d  mov     r8d, 90h; Size
0x18000f033  call    memset_0
0x18000f038  test    rdi, rdi
0x18000f03b  jnz     short loc_18000F06D
0x18000f03d  lea     rax, aCrahelperclass_1; "CRAHelperClass::SetUtilities"
0x18000f044  mov     [rsp+0E0h+var_B8], 80070057h; unsigned int
0x18000f04c  mov     r9d, 641h; unsigned int
0x18000f052  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18000f057  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000f05e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000f063  mov     eax, 80070057h
0x18000f068  jmp     loc_18000F169
0x18000f06d  lea     rbx, [rsi+80h]
0x18000f074  mov     rcx, [rbx]
0x18000f077  test    rcx, rcx
0x18000f07a  jz      short loc_18000F08F
0x18000f07c  mov     rax, [rcx]
0x18000f07f  mov     rax, [rax+10h]
0x18000f083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f088  mov     qword ptr [rbx], 0
0x18000f08f  mov     rax, [rdi]
0x18000f092  lea     rdx, _GUID_91880d0a_a54a_49fd_b232_0064a885c7bf
0x18000f099  mov     r8, rbx
0x18000f09c  mov     rcx, rdi
0x18000f09f  mov     rax, [rax+18h]
0x18000f0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a8  mov     edi, eax
0x18000f0aa  test    eax, eax
0x18000f0ac  jns     short loc_18000F0BD
0x18000f0ae  mov     [rsp+0E0h+var_B8], eax
0x18000f0b2  mov     r9d, 649h
0x18000f0b8  jmp     loc_18000F14F
0x18000f0bd  mov     rcx, [rbx]
0x18000f0c0  lea     rax, aRulegroupname; "rulegroupname"
0x18000f0c7  mov     [rbp+57h+var_B0], rax
0x18000f0cb  lea     rdx, [rbp+57h+var_B0]
0x18000f0cf  lea     rax, psz; "@FirewallAPI.dll,-33002"
0x18000f0d6  mov     [rbp+57h+var_A8], 0Ah
0x18000f0dd  mov     [rbp+57h+var_A0], rax
0x18000f0e1  mov     rax, [rcx]
0x18000f0e4  mov     rax, [rax+18h]
0x18000f0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ed  cmp     dword ptr [rsi+68h], 3
0x18000f0f1  jnz     short loc_18000F141
0x18000f0f3  mov     ecx, 1
0x18000f0f8  lea     rax, aIsinfrahost; "isInfraHost"
0x18000f0ff  mov     [rbp+57h+var_A8], ecx
0x18000f102  lea     rdx, [rbp+57h+var_B0]
0x18000f106  mov     dword ptr [rbp+57h+var_A0], ecx
0x18000f109  mov     rcx, [rbx]
0x18000f10c  mov     [rbp+57h+var_B0], rax
0x18000f110  mov     rax, [rcx]
0x18000f113  mov     rax, [rax+18h]
0x18000f117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11c  mov     rcx, [rbx]
0x18000f11f  lea     rax, aRemoteaccessib; "RemoteAccessibilityIssue"
0x18000f126  mov     [rbp+57h+var_B0], rax
0x18000f12a  lea     rdx, [rbp+57h+var_B0]
0x18000f12e  mov     dword ptr [rbp+57h+var_A0], 0
0x18000f135  mov     rax, [rcx]
0x18000f138  mov     rax, [rax+28h]
0x18000f13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f141  test    eax, eax
0x18000f143  jns     short loc_18000F167
0x18000f145  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000f149  mov     r9d, 669h; unsigned int
0x18000f14f  lea     rax, aCrahelperclass_1; "CRAHelperClass::SetUtilities"
0x18000f156  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000f15d  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18000f162  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000f167  mov     eax, edi
0x18000f169  add     rsp, 0C8h
0x18000f170  pop     rdi
0x18000f171  pop     rsi
0x18000f172  pop     rbx
0x18000f173  pop     rbp
0x18000f174  retn
```
