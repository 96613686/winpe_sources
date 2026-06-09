# ColorFiltering::ColorFilterHelper::IsActive(void)

- ea: `0x1400227c0`
- end: `0x1400228ac`
- name: `?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ`
- size: `236`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400237b8`
- `0x140023ff8`
- `0x140024154`
- `0x1400242b0`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x140017644`
- `0x1400227c0`
- `0x140023ea0`

## string_xrefs

- `0x1400227e4`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
char ColorFiltering::ColorFilterHelper::IsActive(void)
{
  char v0; // bl
  _QWORD v2[3]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v3[3]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v4; // [rsp+60h] [rbp+10h] BYREF

  v0 = 1;
  v4 = 0;
  memset(v2, 0, sizeof(v2));
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v2,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
                       1u)
    || (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v2, L"Active", &v4)
    || !v4 )
  {
    memset(v3, 0, sizeof(v3));
    if ( (unsigned int)ATL::CRegKey::Open(
                         (ATL::CRegKey *)v3,
                         HKEY_CURRENT_USER,
                         L"Software\\Microsoft\\ColorFiltering",
                         1u)
      || (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v3, L"Active", &v4)
      || (ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(v4 != 0), !v4) )
    {
      v0 = 0;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)v3);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v2);
  return v0;
}

```

## disassembly

```asm
0x1400227c0  mov     [rsp-8+arg_8], rbx
0x1400227c5  push    rbp
0x1400227c6  mov     rbp, rsp
0x1400227c9  sub     rsp, 50h
0x1400227cd  mov     ebx, 1
0x1400227d2  mov     [rbp+arg_0], 0
0x1400227d9  mov     r9d, ebx; unsigned int
0x1400227dc  mov     [rbp+var_30], 0
0x1400227e4  lea     r8, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400227eb  mov     [rbp+var_28], 0
0x1400227f3  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1400227fa  mov     [rbp+var_20], 0
0x140022802  lea     rcx, [rbp+var_30]; this
0x140022806  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14002280b  test    eax, eax
0x14002280d  jnz     short loc_14002282C
0x14002280f  lea     r8, [rbp+arg_0]; unsigned int *
0x140022813  lea     rdx, aActive_0; "Active"
0x14002281a  lea     rcx, [rbp+var_30]; this
0x14002281e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140022823  test    eax, eax
0x140022825  jnz     short loc_14002282C
0x140022827  cmp     [rbp+arg_0], eax
0x14002282a  jnz     short loc_140022896
0x14002282c  mov     r9d, ebx; unsigned int
0x14002282f  mov     [rbp+var_18], 0
0x140022837  lea     r8, aSoftwareMicros_17; "Software\\Microsoft\\ColorFiltering"
0x14002283e  mov     [rbp+var_10], 0
0x140022846  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14002284d  mov     [rbp+var_8], 0
0x140022855  lea     rcx, [rbp+var_18]; this
0x140022859  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14002285e  test    eax, eax
0x140022860  jnz     short loc_14002288B
0x140022862  lea     r8, [rbp+arg_0]; unsigned int *
0x140022866  lea     rdx, aActive_0; "Active"
0x14002286d  lea     rcx, [rbp+var_18]; this
0x140022871  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140022876  test    eax, eax
0x140022878  jnz     short loc_14002288B
0x14002287a  cmp     [rbp+arg_0], eax
0x14002287d  setnz   cl; bool
0x140022880  call    ?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)
0x140022885  cmp     [rbp+arg_0], 0
0x140022889  jnz     short loc_14002288D
0x14002288b  xor     bl, bl
0x14002288d  lea     rcx, [rbp+var_18]; this
0x140022891  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140022896  lea     rcx, [rbp+var_30]; this
0x14002289a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14002289f  mov     al, bl
0x1400228a1  mov     rbx, [rsp+50h+arg_8]
0x1400228a6  add     rsp, 50h
0x1400228aa  pop     rbp
0x1400228ab  retn
```
