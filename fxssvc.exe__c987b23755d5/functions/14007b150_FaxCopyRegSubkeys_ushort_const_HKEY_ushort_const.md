# FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)

- ea: `0x14007b150`
- end: `0x14007b2a1`
- name: `?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z`
- size: `337`
- prototype: `unsigned int(const unsigned __int16 *, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14007d9e4`
- `0x14007e844`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400708c4`
- `0x14007b150`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007b24e`
- `ADVAPI32!RegCloseKey` at `0x14007b24e`
- `KERNEL32!GetLastError` at `0x14007b1ba`
- `KERNEL32!GetLastError` at `0x14007b270`
- `KERNEL32!GetLastError` at `0x14007b1ba`
- `KERNEL32!GetLastError` at `0x14007b270`
- `SHLWAPI!SHCopyKeyW` at `0x14007b20f`
- `SHLWAPI!SHCopyKeyW` at `0x14007b20f`

## pseudocode

```c
__int64 __fastcall FaxCopyRegSubkeys(const unsigned __int16 *a1, HKEY a2, const unsigned __int16 *a3)
{
  HKEY v5; // rax
  HKEY v6; // rdi
  DWORD v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v5 = OpenRegistryKey(HKEY_LOCAL_MACHINE, a1, 1, 0x20006u);
  v6 = v5;
  if ( v5 )
  {
    v9 = SHCopyKeyW(HKEY_LOCAL_MACHINE, a3, v5, 0);
    v8 = v9;
    if ( v9
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v9);
    }
    if ( RegCloseKey(v6)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v7);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14007b150  push    rbx
0x14007b152  push    rsi
0x14007b153  push    rdi
0x14007b154  push    r14
0x14007b156  sub     rsp, 28h
0x14007b15a  mov     rsi, r8
0x14007b15d  mov     rbx, rcx
0x14007b160  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b167  lea     r14, WPP_GLOBAL_Control
0x14007b16e  cmp     rcx, r14
0x14007b171  jz      short loc_14007B194
0x14007b173  test    byte ptr [rcx+1Ch], 2
0x14007b177  jz      short loc_14007B194
0x14007b179  cmp     byte ptr [rcx+19h], 5
0x14007b17d  jb      short loc_14007B194
0x14007b17f  mov     rcx, [rcx+10h]
0x14007b183  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007b18a  mov     edx, 80h
0x14007b18f  call    WPP_SF_
0x14007b194  mov     rdx, rbx
0x14007b197  mov     r9d, 20006h
0x14007b19d  mov     rbx, 0FFFFFFFF80000002h
0x14007b1a4  mov     r8d, 1
0x14007b1aa  mov     rcx, rbx
0x14007b1ad  call    OpenRegistryKey
0x14007b1b2  mov     rdi, rax
0x14007b1b5  test    rax, rax
0x14007b1b8  jnz     short loc_14007B203
0x14007b1ba  call    cs:__imp_GetLastError
0x14007b1c0  mov     ebx, eax
0x14007b1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b1c9  cmp     rcx, r14
0x14007b1cc  jz      loc_14007B295
0x14007b1d2  test    byte ptr [rcx+1Ch], 2
0x14007b1d6  jz      loc_14007B295
0x14007b1dc  cmp     byte ptr [rcx+19h], 2
0x14007b1e0  jb      loc_14007B295
0x14007b1e6  mov     rcx, [rcx+10h]
0x14007b1ea  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007b1f1  mov     edx, 81h
0x14007b1f6  mov     r9d, eax
0x14007b1f9  call    WPP_SF_d
0x14007b1fe  jmp     loc_14007B295
0x14007b203  xor     r9d, r9d; fReserved
0x14007b206  mov     r8, rdi; hkeyDest
0x14007b209  mov     rdx, rsi; pszSrcSubKey
0x14007b20c  mov     rcx, rbx; hkeySrc
0x14007b20f  call    cs:__imp_SHCopyKeyW
0x14007b215  mov     ebx, eax
0x14007b217  test    eax, eax
0x14007b219  jz      short loc_14007B24B
0x14007b21b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b222  cmp     rcx, r14
0x14007b225  jz      short loc_14007B24B
0x14007b227  test    byte ptr [rcx+1Ch], 2
0x14007b22b  jz      short loc_14007B24B
0x14007b22d  cmp     byte ptr [rcx+19h], 2
0x14007b231  jb      short loc_14007B24B
0x14007b233  mov     rcx, [rcx+10h]
0x14007b237  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007b23e  mov     edx, 82h
0x14007b243  mov     r9d, eax
0x14007b246  call    WPP_SF_d
0x14007b24b  mov     rcx, rdi; hKey
0x14007b24e  call    cs:__imp_RegCloseKey
0x14007b254  test    eax, eax
0x14007b256  jz      short loc_14007B295
0x14007b258  mov     rax, cs:WPP_GLOBAL_Control
0x14007b25f  cmp     rax, r14
0x14007b262  jz      short loc_14007B295
0x14007b264  test    byte ptr [rax+1Ch], 2
0x14007b268  jz      short loc_14007B295
0x14007b26a  cmp     byte ptr [rax+19h], 2
0x14007b26e  jb      short loc_14007B295
0x14007b270  call    cs:__imp_GetLastError
0x14007b276  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b27d  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007b284  mov     edx, 83h
0x14007b289  mov     r9d, eax
0x14007b28c  mov     rcx, [rcx+10h]
0x14007b290  call    WPP_SF_d
0x14007b295  mov     eax, ebx
0x14007b297  add     rsp, 28h
0x14007b29b  pop     r14
0x14007b29d  pop     rdi
0x14007b29e  pop     rsi
0x14007b29f  pop     rbx
0x14007b2a0  retn
```
