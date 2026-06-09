# IsFWProfilePublic(void)

- ea: `0x180011874`
- end: `0x180011945`
- name: `?IsFWProfilePublic@@YAHXZ`
- size: `209`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000da10`

## callees

- `0x180011874`
- `0x180014660`
- `0x1800148c4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800118ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800118ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 IsFWProfilePublic(void)
{
  BOOL v0; // ebx
  CEventLogger *v1; // rcx
  HRESULT v2; // edi
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  CEventLogger *v4; // rcx
  signed int v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  int v9; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  ppv = 0;
  v9 = 0;
  v2 = CoCreateInstance(
         &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
         0,
         1u,
         &GUID_98325047_c671_4174_8d81_defcd3f03186,
         &ppv);
  if ( v2 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v9);
    if ( v5 >= 0 )
      v0 = (v9 & 4) != 0;
    else
      CEventLogger::LogError(
        v7,
        v6,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x63Bu,
        L"IsFWProfilePublic",
        v5);
  }
  else
  {
    CEventLogger::LogEvent(v1, &COM_Problem, L"9C4C6277-5027-441E-AFAE-CA1F542DA009");
    CEventLogger::LogError(
      v4,
      v3,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x636u,
      L"IsFWProfilePublic",
      v2);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v0;
}

```

## disassembly

```asm
0x180011874  mov     rax, rsp
0x180011877  mov     [rax+18h], rbx
0x18001187b  mov     [rax+20h], rsi
0x18001187f  push    rdi
0x180011880  sub     rsp, 30h
0x180011884  xor     ebx, ebx
0x180011886  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x18001188d  mov     [rax+10h], rbx
0x180011891  xor     edx, edx; pUnkOuter
0x180011893  mov     [rax+8], ebx
0x180011896  lea     rax, [rax+10h]
0x18001189a  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x1800118a1  mov     [rsp+38h+ppv], rax; ppv
0x1800118a6  lea     esi, [rbx+1]
0x1800118a9  mov     r8d, esi; dwClsContext
0x1800118ac  call    cs:__imp_CoCreateInstance
0x1800118b2  mov     edi, eax
0x1800118b4  test    eax, eax
0x1800118b6  jns     short loc_1800118EF
0x1800118b8  lea     r8, a9c4c6277502744; "9C4C6277-5027-441E-AFAE-CA1F542DA009"
0x1800118bf  lea     rdx, COM_Problem; struct _EVENT_DESCRIPTOR *
0x1800118c6  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x1800118cb  mov     r9d, 636h; unsigned int
0x1800118d1  mov     [rsp+38h+var_10], edi; unsigned int
0x1800118d5  lea     rax, aIsfwprofilepub; "IsFWProfilePublic"
0x1800118dc  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x1800118e3  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x1800118e8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800118ed  jmp     short loc_18001191D
0x1800118ef  mov     rcx, [rsp+38h+arg_8]
0x1800118f4  lea     rdx, [rsp+38h+arg_0]
0x1800118f9  mov     rax, [rcx]
0x1800118fc  mov     rax, [rax+38h]
0x180011900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011905  test    eax, eax
0x180011907  jns     short loc_180011915
0x180011909  mov     [rsp+38h+var_10], eax
0x18001190d  mov     r9d, 63Bh
0x180011913  jmp     short loc_1800118D5
0x180011915  test    byte ptr [rsp+38h+arg_0], 4
0x18001191a  cmovnz  ebx, esi
0x18001191d  mov     rcx, [rsp+38h+arg_8]
0x180011922  test    rcx, rcx
0x180011925  jz      short loc_180011933
0x180011927  mov     rdx, [rcx]
0x18001192a  mov     rax, [rdx+10h]
0x18001192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011933  mov     rsi, [rsp+38h+arg_18]
0x180011938  mov     eax, ebx
0x18001193a  mov     rbx, [rsp+38h+arg_10]
0x18001193f  add     rsp, 30h
0x180011943  pop     rdi
0x180011944  retn
```
