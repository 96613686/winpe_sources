# RegisterCLSID(HKEY__ *,ushort const *)

- ea: `0x140003ea4`
- end: `0x140004101`
- name: `?RegisterCLSID@@YAKPEAUHKEY__@@PEBG@Z`
- size: `605`
- prototype: `unsigned int __fastcall(HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000c498`

## callees

- `0x140001af3`
- `0x140003ea4`
- `0x140004314`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140003f75`
- `ADVAPI32!RegSetValueExW` at `0x14000400f`
- `ADVAPI32!RegSetValueExW` at `0x1400040b4`
- `ADVAPI32!RegSetValueExW` at `0x140003f75`
- `ADVAPI32!RegSetValueExW` at `0x14000400f`
- `ADVAPI32!RegSetValueExW` at `0x1400040b4`
- `ADVAPI32!RegCreateKeyExW` at `0x140003fcf`
- `ADVAPI32!RegCreateKeyExW` at `0x140003fcf`
- `ADVAPI32!RegCloseKey` at `0x1400040c7`
- `ADVAPI32!RegCloseKey` at `0x1400040c7`

## pseudocode

```c
__int64 __fastcall RegisterCLSID(HKEY hKey, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rax
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  BYTE lpData[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[540]; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v13[4]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v14[540]; // [rsp+284h] [rbp+184h] BYREF

  *(_DWORD *)Data = 64;
  memset_0(v12, 0, 0x218u);
  v4 = StringCchCatW((unsigned __int16 *)Data, 0x10Eu, a2);
  if ( !v4 )
  {
    v4 = StringCchCatW((unsigned __int16 *)Data, 0x10Eu, L",-1001");
    if ( !v4 )
    {
      v5 = -1;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&Data[2 * v6] );
      v4 = RegSetValueExW(hKey, L"LocalizedString", 0, 2u, Data, 2 * v6 + 2);
      if ( !v4 )
      {
        hKeya = 0;
        dwDisposition = 0;
        v4 = RegCreateKeyExW(hKey, L"Elevation", 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
        if ( !v4 )
        {
          *(_DWORD *)lpData = 1;
          v4 = RegSetValueExW(hKeya, L"Enabled", 0, 4u, lpData, 4u);
          if ( !v4 )
          {
            *(_DWORD *)v13 = 64;
            memset_0(v14, 0, 0x218u);
            v4 = StringCchCatW((unsigned __int16 *)v13, 0x10Eu, a2);
            if ( !v4 )
            {
              v4 = StringCchCatW((unsigned __int16 *)v13, 0x10Eu, L",-1002");
              if ( !v4 )
              {
                do
                  ++v5;
                while ( *(_WORD *)&v13[2 * v5] );
                v4 = RegSetValueExW(hKeya, L"IconReference", 0, 2u, v13, 2 * v5 + 2);
              }
            }
          }
          RegCloseKey(hKeya);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140003ea4  mov     [rsp-8+arg_10], rbx
0x140003ea9  mov     [rsp-8+arg_18], rsi
0x140003eae  push    rbp
0x140003eaf  push    rdi
0x140003eb0  push    r12
0x140003eb2  push    r14
0x140003eb4  push    r15
0x140003eb6  lea     rbp, [rsp-3B0h]
0x140003ebe  sub     rsp, 4B0h
0x140003ec5  mov     rax, cs:__security_cookie
0x140003ecc  xor     rax, rsp
0x140003ecf  mov     [rbp+3D0h+var_30], rax
0x140003ed6  mov     r14, rdx
0x140003ed9  mov     dword ptr [rsp+4D0h+Data], 40h ; '@'
0x140003ee1  mov     rsi, rcx
0x140003ee4  xor     edx, edx; Val
0x140003ee6  lea     rcx, [rsp+4D0h+var_46C]; void *
0x140003eeb  mov     r8d, 218h; Size
0x140003ef1  call    memset_0
0x140003ef6  mov     r12d, 10Eh
0x140003efc  lea     rcx, [rsp+4D0h+Data]; unsigned __int16 *
0x140003f01  mov     edx, r12d; unsigned __int64
0x140003f04  mov     r8, r14; unsigned __int16 *
0x140003f07  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003f0c  xor     r15d, r15d
0x140003f0f  mov     ebx, eax
0x140003f11  test    eax, eax
0x140003f13  jnz     loc_1400040D3
0x140003f19  lea     r8, a1001; ",-1001"
0x140003f20  mov     edx, r12d; unsigned __int64
0x140003f23  lea     rcx, [rsp+4D0h+Data]; unsigned __int16 *
0x140003f28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003f2d  mov     ebx, eax
0x140003f2f  test    eax, eax
0x140003f31  jnz     loc_1400040D3
0x140003f37  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140003f3b  lea     rcx, [rsp+4D0h+Data]
0x140003f40  mov     rax, rdi
0x140003f43  inc     rax
0x140003f46  cmp     [rcx+rax*2], r15w
0x140003f4b  jnz     short loc_140003F43
0x140003f4d  lea     eax, ds:2[rax*2]
0x140003f54  mov     r9d, 2; dwType
0x140003f5a  mov     [rsp+4D0h+cbData], eax; cbData
0x140003f5e  lea     rdx, aLocalizedstrin; "LocalizedString"
0x140003f65  lea     rax, [rsp+4D0h+Data]
0x140003f6a  xor     r8d, r8d; Reserved
0x140003f6d  mov     rcx, rsi; hKey
0x140003f70  mov     [rsp+4D0h+lpData], rax; lpData
0x140003f75  call    cs:__imp_RegSetValueExW
0x140003f7c  nop     dword ptr [rax+rax+00h]
0x140003f81  mov     ebx, eax
0x140003f83  test    eax, eax
0x140003f85  jnz     loc_1400040D3
0x140003f8b  lea     rax, [rsp+4D0h+dwDisposition]
0x140003f90  mov     [rsp+4D0h+hKey], r15
0x140003f95  mov     [rsp+4D0h+lpdwDisposition], rax; lpdwDisposition
0x140003f9a  lea     r9, Class; "REG_SZ"
0x140003fa1  lea     rax, [rsp+4D0h+hKey]
0x140003fa6  mov     [rsp+4D0h+dwDisposition], r15d
0x140003fab  mov     [rsp+4D0h+phkResult], rax; phkResult
0x140003fb0  lea     rdx, SubKey; "Elevation"
0x140003fb7  mov     [rsp+4D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140003fbc  xor     r8d, r8d; Reserved
0x140003fbf  mov     [rsp+4D0h+cbData], 0F003Fh; samDesired
0x140003fc7  mov     rcx, rsi; hKey
0x140003fca  mov     dword ptr [rsp+4D0h+lpData], r15d; dwOptions
0x140003fcf  call    cs:__imp_RegCreateKeyExW
0x140003fd6  nop     dword ptr [rax+rax+00h]
0x140003fdb  mov     ebx, eax
0x140003fdd  test    eax, eax
0x140003fdf  jnz     loc_1400040D3
0x140003fe5  mov     rcx, [rsp+4D0h+hKey]; hKey
0x140003fea  lea     r9d, [rax+4]; dwType
0x140003fee  lea     rax, [rsp+4D0h+var_474]
0x140003ff3  mov     [rsp+4D0h+cbData], r9d; cbData
0x140003ff8  xor     r8d, r8d; Reserved
0x140003ffb  mov     [rsp+4D0h+lpData], rax; lpData
0x140004000  lea     rdx, aEnabled; "Enabled"
0x140004007  mov     dword ptr [rsp+4D0h+var_474], 1
0x14000400f  call    cs:__imp_RegSetValueExW
0x140004016  nop     dword ptr [rax+rax+00h]
0x14000401b  mov     ebx, eax
0x14000401d  test    eax, eax
0x14000401f  jnz     loc_1400040C2
0x140004025  xor     edx, edx; Val
0x140004027  mov     dword ptr [rbp+3D0h+var_250], 40h ; '@'
0x140004031  mov     r8d, 218h; Size
0x140004037  lea     rcx, [rbp+3D0h+var_24C]; void *
0x14000403e  call    memset_0
0x140004043  mov     r8, r14; unsigned __int16 *
0x140004046  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x14000404d  mov     rdx, r12; unsigned __int64
0x140004050  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004055  mov     ebx, eax
0x140004057  test    eax, eax
0x140004059  jnz     short loc_1400040C2
0x14000405b  lea     r8, a1002; ",-1002"
0x140004062  mov     rdx, r12; unsigned __int64
0x140004065  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x14000406c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004071  mov     ebx, eax
0x140004073  test    eax, eax
0x140004075  jnz     short loc_1400040C2
0x140004077  lea     rax, [rbp+3D0h+var_250]
0x14000407e  inc     rdi
0x140004081  cmp     [rax+rdi*2], r15w
0x140004086  jnz     short loc_14000407E
0x140004088  mov     rcx, [rsp+4D0h+hKey]; hKey
0x14000408d  lea     eax, ds:2[rdi*2]
0x140004094  mov     [rsp+4D0h+cbData], eax; cbData
0x140004098  lea     rdx, aIconreference; "IconReference"
0x14000409f  lea     rax, [rbp+3D0h+var_250]
0x1400040a6  mov     r9d, 2; dwType
0x1400040ac  xor     r8d, r8d; Reserved
0x1400040af  mov     [rsp+4D0h+lpData], rax; lpData
0x1400040b4  call    cs:__imp_RegSetValueExW
0x1400040bb  nop     dword ptr [rax+rax+00h]
0x1400040c0  mov     ebx, eax
0x1400040c2  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1400040c7  call    cs:__imp_RegCloseKey
0x1400040ce  nop     dword ptr [rax+rax+00h]
0x1400040d3  mov     eax, ebx
0x1400040d5  mov     rcx, [rbp+3D0h+var_30]
0x1400040dc  xor     rcx, rsp; StackCookie
0x1400040df  call    __security_check_cookie
0x1400040e4  lea     r11, [rsp+4D0h+var_20]
0x1400040ec  mov     rbx, [r11+40h]
0x1400040f0  mov     rsi, [r11+48h]
0x1400040f4  mov     rsp, r11
0x1400040f7  pop     r15
0x1400040f9  pop     r14
0x1400040fb  pop     r12
0x1400040fd  pop     rdi
0x1400040fe  pop     rbp
0x1400040ff  retn
```
