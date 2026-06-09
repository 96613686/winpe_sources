# ApplyPatch(ushort const *,ushort const *)

- ea: `0x1400041d0`
- end: `0x1400042ab`
- name: `?ApplyPatch@@YAHPEBG0@Z`
- size: `219`
- prototype: `UINT __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400011e4`

## callees

- `0x1400041d0`

## import_xrefs

- `msi!__imp_MsiSetInternalUI` at `0x1400041f2`
- `msi!__imp_MsiSetInternalUI` at `0x1400041f2`
- `msi!__imp_MsiApplyPatchW` at `0x140004290`
- `msi!__imp_MsiApplyPatchW` at `0x140004290`
- `msi!__imp_MsiApplyMultiplePatchesW` at `0x14000427e`
- `msi!__imp_MsiApplyMultiplePatchesW` at `0x14000427e`

## pseudocode

```c
UINT __fastcall ApplyPatch(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  INSTALLUILEVEL v2; // ecx
  INSTALLTYPE v4; // r8d
  const WCHAR *v5; // rdx
  UINT result; // eax
  char v7; // cl
  const unsigned __int16 *i; // rax

  v2 = INSTALLUILEVEL_FULL;
  if ( g_INSTALLUILEVEL != -1 )
    v2 = g_INSTALLUILEVEL;
  MsiSetInternalUI(v2, 0);
  if ( (_WORD)g_szProductToPatch )
  {
    if ( (_WORD)g_szProductToPatch != 65 )
      return 87;
    v4 = INSTALLTYPE_NETWORK_IMAGE;
    v5 = &pszDest;
  }
  else
  {
    v5 = 0;
    v4 = INSTALLTYPE_DEFAULT;
  }
  if ( g_szInstanceToConfigure )
  {
    if ( v4 == INSTALLTYPE_NETWORK_IMAGE )
      return 87;
    v4 = INSTALLTYPE_SINGLE_INSTANCE;
    v5 = &g_szInstanceToConfigure;
  }
  v7 = 0;
  for ( i = a2; *i; ++i )
  {
    if ( *i == 59 )
    {
      v7 = 1;
      break;
    }
  }
  if ( (v4 & 0xFFFFFFFD) != 0 || !v7 )
    result = MsiApplyPatchW(a2, v5, v4, g_szCommandLine);
  else
    result = MsiApplyMultiplePatchesW(
               a2,
               v5,
               (LPCWSTR)((unsigned __int64)g_szCommandLine & -(__int64)(*g_szCommandLine != 0)));
  if ( !result )
    return 0x8000;
  return result;
}

```

## disassembly

```asm
0x1400041d0  mov     [rsp+arg_0], rbx
0x1400041d5  push    rdi
0x1400041d6  sub     rsp, 20h
0x1400041da  cmp     cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A, 0FFFFFFFFh; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x1400041e1  mov     ecx, 5
0x1400041e6  mov     rbx, rdx
0x1400041e9  cmovnz  ecx, cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A; dwUILevel
0x1400041f0  xor     edx, edx; phWnd
0x1400041f2  call    cs:__imp_MsiSetInternalUI
0x1400041f8  movzx   eax, cs:?g_szProductToPatch@@3PAGA; ushort near * g_szProductToPatch
0x1400041ff  xor     edi, edi
0x140004201  test    ax, ax
0x140004204  jz      short loc_140004219
0x140004206  cmp     ax, 41h ; 'A'
0x14000420a  jnz     short loc_14000422E
0x14000420c  lea     r8d, [rdi+1]
0x140004210  lea     rdx, pszDest
0x140004217  jmp     short loc_14000421F
0x140004219  mov     rdx, rdi
0x14000421c  mov     r8d, edi
0x14000421f  cmp     cs:?g_szInstanceToConfigure@@3PAGA, di; ushort near * g_szInstanceToConfigure
0x140004226  jz      short loc_140004242
0x140004228  cmp     r8d, 1
0x14000422c  jnz     short loc_140004235
0x14000422e  mov     eax, 57h ; 'W'
0x140004233  jmp     short loc_1400042A0
0x140004235  mov     r8d, 2; eInstallType
0x14000423b  lea     rdx, ?g_szInstanceToConfigure@@3PAGA; szInstallPackage
0x140004242  mov     cl, dil
0x140004245  mov     rax, rbx
0x140004248  cmp     [rax], di
0x14000424b  jz      short loc_14000425B
0x14000424d  cmp     word ptr [rax], 3Bh ; ';'
0x140004251  jz      short loc_140004259
0x140004253  add     rax, 2
0x140004257  jmp     short loc_140004248
0x140004259  mov     cl, 1
0x14000425b  test    r8d, 0FFFFFFFDh
0x140004262  jnz     short loc_140004286
0x140004264  test    cl, cl
0x140004266  jz      short loc_140004286
0x140004268  mov     rcx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x14000426f  movzx   eax, word ptr [rcx]
0x140004272  neg     ax
0x140004275  sbb     r8, r8
0x140004278  and     r8, rcx; szPropertiesList
0x14000427b  mov     rcx, rbx; szPatchPackages
0x14000427e  call    cs:__imp_MsiApplyMultiplePatchesW
0x140004284  jmp     short loc_140004296
0x140004286  mov     r9, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; szCommandLine
0x14000428d  mov     rcx, rbx; szPatchPackage
0x140004290  call    cs:__imp_MsiApplyPatchW
0x140004296  test    eax, eax
0x140004298  mov     ecx, 8000h
0x14000429d  cmovz   eax, ecx
0x1400042a0  mov     rbx, [rsp+28h+arg_0]
0x1400042a5  add     rsp, 20h
0x1400042a9  pop     rdi
0x1400042aa  retn
```
