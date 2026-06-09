# OSKSettingsManager::SetOskSetting(ulong,ulong,int)

- ea: `0x140017888`
- end: `0x14001798a`
- name: `?SetOskSetting@OSKSettingsManager@@QEAAJKKH@Z`
- size: `258`
- prototype: `__int64 __fastcall(OSKSettingsManager *__hidden this, unsigned int, unsigned int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400174f8`
- `0x14001783c`
- `0x1400179b0`
- `0x140017a6c`

## callees

- `0x140005c90`
- `0x1400170d8`
- `0x1400175e8`
- `0x140017888`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140017934`
- `ADVAPI32!RegSetValueExW` at `0x140017934`

## string_xrefs

- `0x1400178e6`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\osk`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSKSettingsManager::SetOskSetting(
        OSKSettingsManager *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  int v4; // esi
  __int64 v5; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  HKEY v10; // [rsp+30h] [rbp-58h]
  HKEY hKey[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+18h] BYREF

  Data = a3;
  v4 = (int)a4;
  v5 = a2;
  if ( a2 >= 0x14 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    memset(hKey, 0, 24);
    if ( (_DWORD)a4 )
      v7 = ATL::CRegKey::Create(
             (ATL::CRegKey *)hKey,
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\osk",
             a4,
             1u,
             0x2001Fu,
             v10,
             0);
    else
      v7 = ATL::CRegKey::Create(
             (ATL::CRegKey *)hKey,
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Osk",
             a4,
             0,
             0x2001Fu,
             v10,
             0);
    if ( v7 )
    {
      v8 = -2147467259;
    }
    else
    {
      if ( RegSetValueExW(hKey[0], (LPCWSTR)*(&g_rgOskSettings + 3 * v5), 0, 4u, (const BYTE *)&Data, 4u) )
      {
        v8 = -2147467259;
      }
      else
      {
        v8 = 0;
        if ( !v4 )
          OSKSettingsManager::NotifyListeners(this, v5, Data);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  return v8;
}

```

## disassembly

```asm
0x140017888  mov     rax, rsp
0x14001788b  mov     [rax+18h], r8d
0x14001788f  push    rbx
0x140017890  push    rbp
0x140017891  push    rsi
0x140017892  push    rdi
0x140017893  sub     rsp, 68h
0x140017897  mov     esi, r9d
0x14001789a  mov     edi, edx
0x14001789c  mov     rbp, rcx
0x14001789f  cmp     edx, 14h
0x1400178a2  jnb     loc_14001797A
0x1400178a8  mov     qword ptr [rax-48h], 0
0x1400178b0  mov     qword ptr [rax-40h], 0
0x1400178b8  mov     qword ptr [rax-38h], 0
0x1400178c0  mov     qword ptr [rax-50h], 0
0x1400178c8  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1400178cf  lea     rcx, [rax-48h]; this
0x1400178d3  mov     dword ptr [rax-60h], 2001Fh
0x1400178da  test    r9d, r9d
0x1400178dd  jz      short loc_1400178EF
0x1400178df  mov     dword ptr [rax-68h], 1
0x1400178e6  lea     r8, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400178ed  jmp     short loc_1400178FE
0x1400178ef  mov     dword ptr [rsp+88h+lpData], 0; DWORD
0x1400178f7  lea     r8, aSoftwareMicros_9; "Software\\Microsoft\\Osk"
0x1400178fe  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140017903  test    eax, eax
0x140017905  jnz     short loc_140017969
0x140017907  lea     rdx, [rdi+rdi*2]
0x14001790b  lea     rcx, ?g_rgOskSettings@@3PAU_OSKSETTINGSINFO@@A; _OSKSETTINGSINFO near * g_rgOskSettings
0x140017912  lea     r9d, [rax+4]; dwType
0x140017916  mov     [rsp+88h+cbData], r9d; cbData
0x14001791b  lea     rax, [rsp+88h+Data]
0x140017923  mov     [rsp+88h+lpData], rax; lpData
0x140017928  xor     r8d, r8d; Reserved
0x14001792b  mov     rdx, [rcx+rdx*8]; lpValueName
0x14001792f  mov     rcx, [rsp+88h+hKey]; hKey
0x140017934  call    cs:__imp_RegSetValueExW
0x14001793a  test    eax, eax
0x14001793c  jnz     short loc_140017958
0x14001793e  xor     ebx, ebx
0x140017940  test    esi, esi
0x140017942  jnz     short loc_14001795D
0x140017944  mov     r8d, [rsp+88h+Data]; unsigned int
0x14001794c  mov     edx, edi; unsigned int
0x14001794e  mov     rcx, rbp; this
0x140017951  call    ?NotifyListeners@OSKSettingsManager@@QEAAXKK@Z; OSKSettingsManager::NotifyListeners(ulong,ulong)
0x140017956  jmp     short loc_14001795D
0x140017958  mov     ebx, 80004005h
0x14001795d  lea     rcx, [rsp+88h+hKey]; this
0x140017962  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017967  jmp     short loc_14001796E
0x140017969  mov     ebx, 80004005h
0x14001796e  lea     rcx, [rsp+88h+hKey]; this
0x140017973  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017978  jmp     short loc_14001797F
0x14001797a  mov     ebx, 80004005h
0x14001797f  mov     eax, ebx
0x140017981  add     rsp, 68h
0x140017985  pop     rdi
0x140017986  pop     rsi
0x140017987  pop     rbp
0x140017988  pop     rbx
0x140017989  retn
```
