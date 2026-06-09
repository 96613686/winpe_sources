# CacheSurrogateFontData(tag_STRING_ANALYSIS *)

- ea: `0x180032910`
- end: `0x180032b4f`
- name: `?CacheSurrogateFontData@@YAXPEAUtag_STRING_ANALYSIS@@@Z`
- size: `575`
- prototype: `void __fastcall(struct tag_STRING_ANALYSIS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007490`

## callees

- `0x18000d040`
- `0x18000d410`
- `0x180032910`
- `0x180032b58`
- `0x180032cd0`
- `0x180032d48`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032a19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032ac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032b27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032a19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032ac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032b27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800329c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032a01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032a65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800329c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032a01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032a65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032a91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032aed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032a91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032aed`
- `win32u!NtGdiGetTextFaceW` at `0x180032994`
- `win32u!NtGdiGetTextFaceW` at `0x180032994`

## pseudocode

```c
void __fastcall CacheSurrogateFontData(struct tag_STRING_ANALYSIS *a1)
{
  __int64 v2; // rcx
  bool v3; // zf
  const WCHAR *SurrogateBaseFaceName; // rax
  char *v5; // rax
  char *v6; // rbx
  char *v7; // rax
  char *v8; // rbx
  HKEY hKey; // [rsp+30h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-21h] BYREF
  wchar_t v11[32]; // [rsp+40h] [rbp-19h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( gSurrogateFontTable == (char *)-1LL )
  {
    gSurrogateFontTable = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\SurrogateFallback",
            0,
            0x101u,
            &hKey) )
    {
      if ( (unsigned int)CheckInitUspMemory() )
      {
        v5 = (char *)HeapAlloc(ghHeap, 0, 0x200u);
        v6 = v5;
        if ( v5 )
        {
          if ( (unsigned int)CopySurrogatePlaneListFromRegKey(hKey, v5) )
            UspFreeMem(v6);
          else
            gSurrogateFontTable = v6;
        }
      }
      RegCloseKey(hKey);
    }
  }
  v2 = *(_QWORD *)(*((_QWORD *)a1 + 55) + 80LL);
  if ( *(_QWORD *)(v2 + 2144) == -1 )
  {
    v3 = gSurrogateFontTable == 0;
    *(_QWORD *)(v2 + 2144) = 0;
    if ( !v3 )
    {
      memset_0(v11, 0, sizeof(v11));
      NtGdiGetTextFaceW(*(_QWORD *)a1, 32, v11);
      if ( v11[0] )
      {
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\SurrogateFallback",
                0,
                0x109u,
                &hKey) )
        {
          CreateLocalizedNameXlateTable(hKey);
          SurrogateBaseFaceName = GetSurrogateBaseFaceName(v11);
          if ( !RegOpenKeyExW(hKey, SurrogateBaseFaceName, 0, 0x101u, &phkResult) )
          {
            if ( (unsigned int)CheckInitUspMemory() )
            {
              v7 = (char *)HeapAlloc(ghHeap, 0, 0x200u);
              v8 = v7;
              if ( v7 )
              {
                if ( (unsigned int)CopySurrogatePlaneListFromRegKey(phkResult, v7) )
                  UspFreeMem(v8);
                else
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 55) + 80LL) + 2144LL) = v8;
              }
            }
            RegCloseKey(phkResult);
          }
          RegCloseKey(hKey);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180032910  push    rbp
0x180032912  push    rbx
0x180032913  push    rsi
0x180032914  push    rdi
0x180032915  lea     rbp, [rsp-3Fh]
0x18003291a  sub     rsp, 98h
0x180032921  mov     rax, cs:__security_cookie
0x180032928  xor     rax, rsp
0x18003292b  mov     [rbp+57h+var_30], rax
0x18003292f  xor     esi, esi
0x180032931  mov     rdi, rcx
0x180032934  cmp     cs:?gSurrogateFontTable@@3PEADEA, 0FFFFFFFFFFFFFFFFh; char * gSurrogateFontTable
0x18003293c  mov     [rbp+57h+hKey], rsi
0x180032940  mov     [rbp+57h+var_78], rsi
0x180032944  jz      loc_180032A3E
0x18003294a  mov     rax, [rdi+1B8h]
0x180032951  mov     rcx, [rax+50h]
0x180032955  cmp     qword ptr [rcx+860h], 0FFFFFFFFFFFFFFFFh
0x18003295d  jnz     loc_180032A25
0x180032963  cmp     cs:?gSurrogateFontTable@@3PEADEA, rsi; char * gSurrogateFontTable
0x18003296a  mov     [rcx+860h], rsi
0x180032971  jz      loc_180032A25
0x180032977  xor     edx, edx; Val
0x180032979  lea     rcx, [rbp+57h+var_70]; void *
0x18003297d  lea     r8d, [rdx+40h]; Size
0x180032981  call    memset_0
0x180032986  mov     rcx, [rdi]
0x180032989  lea     r8, [rbp+57h+var_70]
0x18003298d  xor     r9d, r9d
0x180032990  lea     edx, [r9+20h]
0x180032994  call    cs:__imp_NtGdiGetTextFaceW
0x18003299b  nop     dword ptr [rax+rax+00h]
0x1800329a0  cmp     [rbp+57h+var_70], si
0x1800329a4  jz      short loc_180032A25
0x1800329a6  lea     rax, [rbp+57h+hKey]
0x1800329aa  mov     r9d, 109h; samDesired
0x1800329b0  xor     r8d, r8d; ulOptions
0x1800329b3  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800329b8  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800329bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800329c6  call    cs:__imp_RegOpenKeyExW
0x1800329cd  nop     dword ptr [rax+rax+00h]
0x1800329d2  test    eax, eax
0x1800329d4  jnz     short loc_180032A25
0x1800329d6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800329da  call    ?CreateLocalizedNameXlateTable@@YAXPEAUHKEY__@@@Z; CreateLocalizedNameXlateTable(HKEY__ *)
0x1800329df  lea     rcx, [rbp+57h+var_70]; wchar_t *
0x1800329e3  call    ?GetSurrogateBaseFaceName@@YAPEA_WPEA_W@Z; GetSurrogateBaseFaceName(wchar_t *)
0x1800329e8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800329ec  mov     rdx, rax; lpSubKey
0x1800329ef  lea     rax, [rbp+57h+var_78]
0x1800329f3  mov     r9d, 101h; samDesired
0x1800329f9  xor     r8d, r8d; ulOptions
0x1800329fc  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180032a01  call    cs:__imp_RegOpenKeyExW
0x180032a08  nop     dword ptr [rax+rax+00h]
0x180032a0d  test    eax, eax
0x180032a0f  jz      loc_180032AD5
0x180032a15  mov     rcx, [rbp+57h+hKey]; hKey
0x180032a19  call    cs:__imp_RegCloseKey
0x180032a20  nop     dword ptr [rax+rax+00h]
0x180032a25  mov     rcx, [rbp+57h+var_30]
0x180032a29  xor     rcx, rsp; StackCookie
0x180032a2c  call    __security_check_cookie
0x180032a31  add     rsp, 98h
0x180032a38  pop     rdi
0x180032a39  pop     rsi
0x180032a3a  pop     rbx
0x180032a3b  pop     rbp
0x180032a3c  retn
0x180032a3e  lea     rax, [rbp+57h+hKey]
0x180032a42  mov     cs:?gSurrogateFontTable@@3PEADEA, rsi; char * gSurrogateFontTable
0x180032a49  mov     r9d, 101h; samDesired
0x180032a4f  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180032a54  xor     r8d, r8d; ulOptions
0x180032a57  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180032a5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032a65  call    cs:__imp_RegOpenKeyExW
0x180032a6c  nop     dword ptr [rax+rax+00h]
0x180032a71  test    eax, eax
0x180032a73  jnz     loc_18003294A
0x180032a79  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x180032a7e  test    eax, eax
0x180032a80  jz      short loc_180032AC0
0x180032a82  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x180032a89  xor     edx, edx; dwFlags
0x180032a8b  mov     r8d, 200h; dwBytes
0x180032a91  call    cs:__imp_HeapAlloc
0x180032a98  nop     dword ptr [rax+rax+00h]
0x180032a9d  mov     rbx, rax
0x180032aa0  test    rax, rax
0x180032aa3  jz      short loc_180032AC0
0x180032aa5  mov     rcx, [rbp+57h+hKey]; hKey
0x180032aa9  mov     rdx, rax; char *
0x180032aac  call    ?CopySurrogatePlaneListFromRegKey@@YAJPEAUHKEY__@@PEAD@Z; CopySurrogatePlaneListFromRegKey(HKEY__ *,char *)
0x180032ab1  test    eax, eax
0x180032ab3  jnz     loc_180032B42
0x180032ab9  mov     cs:?gSurrogateFontTable@@3PEADEA, rbx; char * gSurrogateFontTable
0x180032ac0  mov     rcx, [rbp+57h+hKey]; hKey
0x180032ac4  call    cs:__imp_RegCloseKey
0x180032acb  nop     dword ptr [rax+rax+00h]
0x180032ad0  jmp     loc_18003294A
0x180032ad5  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x180032ada  test    eax, eax
0x180032adc  jz      short loc_180032B23
0x180032ade  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x180032ae5  xor     edx, edx; dwFlags
0x180032ae7  mov     r8d, 200h; dwBytes
0x180032aed  call    cs:__imp_HeapAlloc
0x180032af4  nop     dword ptr [rax+rax+00h]
0x180032af9  mov     rbx, rax
0x180032afc  test    rax, rax
0x180032aff  jz      short loc_180032B23
0x180032b01  mov     rcx, [rbp+57h+var_78]; hKey
0x180032b05  mov     rdx, rax; char *
0x180032b08  call    ?CopySurrogatePlaneListFromRegKey@@YAJPEAUHKEY__@@PEAD@Z; CopySurrogatePlaneListFromRegKey(HKEY__ *,char *)
0x180032b0d  test    eax, eax
0x180032b0f  jnz     short loc_180032B38
0x180032b11  mov     rcx, [rdi+1B8h]
0x180032b18  mov     rdx, [rcx+50h]
0x180032b1c  mov     [rdx+860h], rbx
0x180032b23  mov     rcx, [rbp+57h+var_78]; hKey
0x180032b27  call    cs:__imp_RegCloseKey
0x180032b2e  nop     dword ptr [rax+rax+00h]
0x180032b33  jmp     loc_180032A15
0x180032b38  mov     rcx, rbx; lpMem
0x180032b3b  call    UspFreeMem
0x180032b40  jmp     short loc_180032B23
0x180032b42  mov     rcx, rbx; lpMem
0x180032b45  call    UspFreeMem
0x180032b4a  jmp     loc_180032AC0
```
