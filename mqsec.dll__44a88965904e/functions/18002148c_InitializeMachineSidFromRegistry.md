# InitializeMachineSidFromRegistry

- ea: `0x18002148c`
- end: `0x1800215a0`
- name: `InitializeMachineSidFromRegistry`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021890`

## callees

- `0x18000c39c`
- `0x18001722c`
- `0x18001786c`
- `0x1800178f4`
- `0x180020680`
- `0x18002148c`

## import_xrefs

- `msvcrt!free` at `0x180021503`
- `msvcrt!free` at `0x180021503`

## string_xrefs

- `0x1800214a4`: `security`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int InitializeMachineSidFromRegistry()
{
  unsigned int v0; // esi
  void *v1; // rbx
  unsigned int ValueSize; // eax
  unsigned int v3; // edi
  PVOID *v4; // rax
  int v6; // [rsp+20h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+28h] [rbp-30h]
  const wchar_t *v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+38h] [rbp-20h]
  __int64 v10; // [rsp+40h] [rbp-18h]

  v6 = 1;
  v7 = L"security";
  v8 = L"MachineAccount";
  v9 = 0;
  v10 = 0;
  v0 = 0;
  v1 = 0;
  try
  {
    ValueSize = QueryValueSize((struct RegEntry *)&v6);
    v3 = ValueSize;
    if ( ValueSize )
    {
      v1 = MmAllocate(ValueSize);
      QueryValueInternal((struct RegEntry *)&v6);
      v0 = v3;
      free(0);
    }
  }
  catch ( std::bad_alloc )
  {
    v1 = 0;
    v0 = 0;
  }
  g_pLocalMachineSid = v1;
  LODWORD(g_dwLocalMachineSidLen) = v0;
  if ( v1 )
  {
    v4 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      LODWORD(v4) = WPP_SF__sid_(
                      *((_QWORD *)WPP_GLOBAL_Control + 32),
                      0x1Fu,
                      (const GUID *)WPP_efe327766876393cacc144e0c735893e_Traceguids,
                      (char *)v1);
  }
  else
  {
    v4 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      LODWORD(v4) = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 30, WPP_efe327766876393cacc144e0c735893e_Traceguids);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18002148c  mov     r11, rsp
0x18002148f  mov     [r11+18h], rbx
0x180021493  mov     [r11+20h], rsi
0x180021497  push    rdi
0x180021498  sub     rsp, 50h
0x18002149c  mov     [rsp+58h+var_38], 1
0x1800214a4  lea     rax, aSecurity; "security"
0x1800214ab  mov     [r11-30h], rax
0x1800214af  lea     rax, aMachineaccount; "MachineAccount"
0x1800214b6  mov     [r11-28h], rax
0x1800214ba  mov     [rsp+58h+var_20], 0
0x1800214c2  mov     qword ptr [r11-18h], 0
0x1800214ca  xor     esi, esi
0x1800214cc  xor     ebx, ebx
0x1800214ce  lea     rcx, [r11-38h]; struct RegEntry *
0x1800214d2  call    QueryValueSize
0x1800214d7  mov     edi, eax
0x1800214d9  test    eax, eax
0x1800214db  jz      short loc_18002150A
0x1800214dd  mov     ecx, edi; unsigned __int64
0x1800214df  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800214e4  mov     rbx, rax
0x1800214e7  mov     [rsp+58h+arg_0], rax
0x1800214ec  mov     r9d, edi
0x1800214ef  mov     r8, rax
0x1800214f2  lea     edx, [rsi+3]
0x1800214f5  lea     rcx, [rsp+58h+var_38]; struct RegEntry *
0x1800214fa  call    QueryValueInternal
0x1800214ff  mov     esi, edi
0x180021501  xor     ecx, ecx; Block
0x180021503  call    cs:__imp_free
0x180021509  nop
0x18002150a  jmp     short loc_180021513
0x18002150c  mov     rbx, [rsp+58h+arg_8]
0x180021511  mov     esi, ebx
0x180021513  mov     cs:?g_pLocalMachineSid@@3PEAXEA, rbx; void * g_pLocalMachineSid
0x18002151a  mov     cs:?g_dwLocalMachineSidLen@@3KA, esi; ulong g_dwLocalMachineSidLen
0x180021520  test    rbx, rbx
0x180021523  jnz     short loc_180021559
0x180021525  lea     rax, WPP_GLOBAL_Control
0x18002152c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021533  cmp     rcx, rax
0x180021536  jz      short loc_180021590
0x180021538  test    byte ptr [rcx+10Ch], 4
0x18002153f  jz      short loc_180021590
0x180021541  lea     edx, [rbx+1Eh]
0x180021544  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x18002154b  mov     rcx, [rcx+100h]
0x180021552  call    WPP_SF_
0x180021557  jmp     short loc_180021590
0x180021559  lea     rax, WPP_GLOBAL_Control
0x180021560  mov     rcx, cs:WPP_GLOBAL_Control
0x180021567  cmp     rcx, rax
0x18002156a  jz      short loc_180021590
0x18002156c  test    byte ptr [rcx+10Ch], 4
0x180021573  jz      short loc_180021590
0x180021575  mov     edx, 1Fh
0x18002157a  mov     r9, rbx
0x18002157d  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180021584  mov     rcx, [rcx+100h]; LoggerHandle
0x18002158b  call    WPP_SF__sid_
0x180021590  mov     rbx, [rsp+58h+arg_10]
0x180021595  mov     rsi, [rsp+58h+arg_18]
0x18002159a  add     rsp, 50h
0x18002159e  pop     rdi
0x18002159f  retn
```
