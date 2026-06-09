# PostEntryDeleteProcessing

- ea: `0x1800546f4`
- end: `0x180054aaa`
- name: `PostEntryDeleteProcessing`
- size: `950`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005e408`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800546f4`
- `0x1800554d8`
- `0x18005c710`
- `0x1800635cc`
- `0x180064d10`
- `0x1800663c0`
- `0x1800acf50`
- `0x1800e7206`
- `0x1800e7236`
- `0x1800e7260`
- `0x1800e7320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054771`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054771`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054a51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800547d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800547d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054870`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800547c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180054862`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800547c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180054862`

## pseudocode

```c
__int64 __fastcall PostEntryDeleteProcessing(wchar_t *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  HKEY v8; // rdi
  struct _LIST_ENTRY *v9; // rcx
  int v10; // eax
  HKEY v11; // rdi
  unsigned int v12; // eax
  unsigned int v13; // eax
  _BYTE *v14; // rax
  wchar_t *v15; // rcx
  unsigned int TriggerProfile; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[792]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v20; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v21[9998]; // [rsp+672h] [rbp+572h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 67, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
  }
  v6 = 0;
  EnterCriticalSection(&g_csSubmitRequest);
  memset_0(String1, 0, 0x202u);
  hKey[0] = 0;
  if ( !(unsigned int)RasGetDefIntConnName(0, String1, hKey) )
  {
    v7 = wcsncmp_0(String1, a1, 0x101u);
    v8 = hKey[0];
    if ( !v7 )
      RegDeleteValueA(hKey[0], "DefaultInternet");
    if ( v8 )
      RegCloseKey(v8);
    goto LABEL_15;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 68, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
LABEL_15:
    v9 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(a2 + 8) )
    goto LABEL_27;
  if ( !(unsigned int)RasGetDefIntConnName(1, String1, hKey) )
  {
    v10 = wcsncmp_0(String1, a1, 0x101u);
    v11 = hKey[0];
    if ( !v10 )
      RegDeleteValueA(hKey[0], "DefaultInternet");
    if ( v11 )
      RegCloseKey(v11);
    goto LABEL_26;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 69, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
LABEL_26:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_27:
  if ( (*(_DWORD *)(a2 + 32) & 0x400) == 0 )
  {
    v20 = 0;
    memset_0(v21, 0, sizeof(v21));
    memset_0(String1, 0, sizeof(String1));
    GetUserSid(&v20);
    v12 = SetEntryDialParams((int)&v20, *(_DWORD *)(a3 + 456), -1073741824, 0, String1);
    if ( v12
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 70, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, v12);
    }
    v13 = RasSetKey(*(_OWORD **)(a3 + 464));
    v6 = v13;
    if ( !v13 )
      goto LABEL_38;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 71, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, v13);
LABEL_38:
      v9 = WPP_GLOBAL_Control;
    }
  }
  v14 = *(_BYTE **)(a3 + 448);
  if ( v14
    && *v14
    && v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v9[1].Blink) & 0x2000) != 0
    && BYTE1(v9[1].Blink) >= 2u )
  {
    WPP_SF_(v9[1].Flink, 72, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
  }
  if ( *(_DWORD *)(a3 + 704) )
  {
    v15 = *(wchar_t **)a2;
    LODWORD(hKey[0]) = 0;
    IsActiveAutoTriggerConnectionInternal(v15, a1);
    if ( LODWORD(hKey[0]) )
    {
      TriggerProfile = RasSelectNextTriggerProfile();
      if ( TriggerProfile )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 73, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, TriggerProfile);
        }
      }
    }
    v6 = 0;
  }
  LeaveCriticalSection(&g_csSubmitRequest);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 74, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800546f4  push    rbp
0x1800546f6  push    rbx
0x1800546f7  push    rsi
0x1800546f8  push    rdi
0x1800546f9  push    r13
0x1800546fb  push    r14
0x1800546fd  push    r15
0x1800546ff  lea     rbp, [rsp-2C90h]
0x180054707  mov     eax, 2D90h
0x18005470c  call    _alloca_probe
0x180054711  sub     rsp, rax
0x180054714  mov     rax, cs:__security_cookie
0x18005471b  xor     rax, rsp
0x18005471e  mov     [rbp+2CC0h+var_40], rax
0x180054725  mov     rsi, r8
0x180054728  mov     r14, rdx
0x18005472b  mov     r15, rcx
0x18005472e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054735  lea     rdi, WPP_GLOBAL_Control
0x18005473c  mov     r13d, 2000h
0x180054742  cmp     rcx, rdi
0x180054745  jz      short loc_180054768
0x180054747  test    [rcx+1Ch], r13d
0x18005474b  jz      short loc_180054768
0x18005474d  cmp     byte ptr [rcx+19h], 6
0x180054751  jb      short loc_180054768
0x180054753  mov     rcx, [rcx+10h]
0x180054757  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x18005475e  mov     edx, 43h ; 'C'
0x180054763  call    WPP_SF_
0x180054768  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18005476f  xor     ebx, ebx
0x180054771  call    cs:__imp_EnterCriticalSection
0x180054777  xor     edx, edx; Val
0x180054779  lea     rcx, [rsp+2DC0h+String1]; void *
0x18005477e  mov     r8d, 202h; Size
0x180054784  call    memset_0
0x180054789  lea     r8, [rsp+2DC0h+hKey]
0x18005478e  mov     [rsp+2DC0h+hKey], rbx
0x180054793  lea     rdx, [rsp+2DC0h+String1]
0x180054798  xor     ecx, ecx
0x18005479a  call    RasGetDefIntConnName
0x18005479f  test    eax, eax
0x1800547a1  jnz     short loc_1800547E6
0x1800547a3  mov     r8d, 101h; MaxCount
0x1800547a9  lea     rcx, [rsp+2DC0h+String1]; String1
0x1800547ae  mov     rdx, r15; String2
0x1800547b1  call    wcsncmp_0
0x1800547b6  mov     rdi, [rsp+2DC0h+hKey]
0x1800547bb  test    eax, eax
0x1800547bd  jnz     short loc_1800547CF
0x1800547bf  lea     rdx, aDefaultinterne_0; "DefaultInternet"
0x1800547c6  mov     rcx, rdi; hKey
0x1800547c9  call    cs:__imp_RegDeleteValueA
0x1800547cf  test    rdi, rdi
0x1800547d2  jz      short loc_1800547DD
0x1800547d4  mov     rcx, rdi; hKey
0x1800547d7  call    cs:__imp_RegCloseKey
0x1800547dd  lea     rdi, WPP_GLOBAL_Control
0x1800547e4  jmp     short loc_180054813
0x1800547e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547ed  cmp     rcx, rdi
0x1800547f0  jz      short loc_18005481A
0x1800547f2  test    [rcx+1Ch], r13d
0x1800547f6  jz      short loc_18005481A
0x1800547f8  cmp     byte ptr [rcx+19h], 3
0x1800547fc  jb      short loc_18005481A
0x1800547fe  mov     rcx, [rcx+10h]
0x180054802  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180054809  mov     edx, 44h ; 'D'
0x18005480e  call    WPP_SF_
0x180054813  mov     rcx, cs:WPP_GLOBAL_Control
0x18005481a  cmp     [r14+8], ebx
0x18005481e  jnz     loc_1800548AC
0x180054824  lea     r8, [rsp+2DC0h+hKey]
0x180054829  mov     ecx, 1
0x18005482e  lea     rdx, [rsp+2DC0h+String1]
0x180054833  call    RasGetDefIntConnName
0x180054838  test    eax, eax
0x18005483a  jnz     short loc_180054878
0x18005483c  mov     r8d, 101h; MaxCount
0x180054842  lea     rcx, [rsp+2DC0h+String1]; String1
0x180054847  mov     rdx, r15; String2
0x18005484a  call    wcsncmp_0
0x18005484f  mov     rdi, [rsp+2DC0h+hKey]
0x180054854  test    eax, eax
0x180054856  jnz     short loc_180054868
0x180054858  lea     rdx, aDefaultinterne_0; "DefaultInternet"
0x18005485f  mov     rcx, rdi; hKey
0x180054862  call    cs:__imp_RegDeleteValueA
0x180054868  test    rdi, rdi
0x18005486b  jz      short loc_1800548A5
0x18005486d  mov     rcx, rdi; hKey
0x180054870  call    cs:__imp_RegCloseKey
0x180054876  jmp     short loc_1800548A5
0x180054878  mov     rcx, cs:WPP_GLOBAL_Control
0x18005487f  cmp     rcx, rdi
0x180054882  jz      short loc_1800548AC
0x180054884  test    [rcx+1Ch], r13d
0x180054888  jz      short loc_1800548AC
0x18005488a  cmp     byte ptr [rcx+19h], 3
0x18005488e  jb      short loc_1800548AC
0x180054890  mov     rcx, [rcx+10h]
0x180054894  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x18005489b  mov     edx, 45h ; 'E'
0x1800548a0  call    WPP_SF_
0x1800548a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800548ac  test    dword ptr [r14+20h], 400h
0x1800548b4  jnz     loc_1800549A9
0x1800548ba  xor     eax, eax
0x1800548bc  lea     rcx, [rbp+2CC0h+var_274E]; void *
0x1800548c3  xor     edx, edx; Val
0x1800548c5  mov     [rbp+2CC0h+var_2750], ax
0x1800548cc  mov     r8d, 270Eh; Size
0x1800548d2  call    memset_0
0x1800548d7  xor     edx, edx; Val
0x1800548d9  lea     rcx, [rsp+2DC0h+String1]; void *
0x1800548de  mov     r8d, 630h; Size
0x1800548e4  call    memset_0
0x1800548e9  lea     rcx, [rbp+2CC0h+var_2750]
0x1800548f0  call    GetUserSid
0x1800548f5  mov     edx, [rsi+1C8h]
0x1800548fb  lea     rax, [rsp+2DC0h+String1]
0x180054900  xor     r9d, r9d
0x180054903  mov     [rsp+2DC0h+var_2DA0], rax
0x180054908  mov     r8d, 0C0000000h
0x18005490e  lea     rcx, [rbp+2CC0h+var_2750]
0x180054915  call    SetEntryDialParams
0x18005491a  test    eax, eax
0x18005491c  jz      short loc_180054957
0x18005491e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054925  lea     rdi, WPP_GLOBAL_Control
0x18005492c  cmp     rcx, rdi
0x18005492f  jz      short loc_18005495E
0x180054931  test    [rcx+1Ch], r13d
0x180054935  jz      short loc_18005495E
0x180054937  cmp     byte ptr [rcx+19h], 2
0x18005493b  jb      short loc_18005495E
0x18005493d  mov     rcx, [rcx+10h]
0x180054941  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180054948  mov     edx, 46h ; 'F'
0x18005494d  mov     r9d, eax
0x180054950  call    WPP_SF_d
0x180054955  jmp     short loc_18005495E
0x180054957  lea     rdi, WPP_GLOBAL_Control
0x18005495e  mov     rcx, [rsi+1D0h]
0x180054965  call    RasSetKey
0x18005496a  mov     ebx, eax
0x18005496c  test    eax, eax
0x18005496e  jz      short loc_1800549A0
0x180054970  mov     rcx, cs:WPP_GLOBAL_Control
0x180054977  cmp     rcx, rdi
0x18005497a  jz      short loc_1800549B0
0x18005497c  test    [rcx+1Ch], r13d
0x180054980  jz      short loc_1800549B0
0x180054982  cmp     byte ptr [rcx+19h], 2
0x180054986  jb      short loc_1800549B0
0x180054988  mov     rcx, [rcx+10h]
0x18005498c  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180054993  mov     edx, 47h ; 'G'
0x180054998  mov     r9d, eax
0x18005499b  call    WPP_SF_d
0x1800549a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800549a7  jmp     short loc_1800549B0
0x1800549a9  lea     rdi, WPP_GLOBAL_Control
0x1800549b0  mov     rax, [rsi+1C0h]
0x1800549b7  test    rax, rax
0x1800549ba  jz      short loc_1800549E7
0x1800549bc  cmp     byte ptr [rax], 0
0x1800549bf  jz      short loc_1800549E7
0x1800549c1  cmp     rcx, rdi
0x1800549c4  jz      short loc_1800549E7
0x1800549c6  test    [rcx+1Ch], r13d
0x1800549ca  jz      short loc_1800549E7
0x1800549cc  cmp     byte ptr [rcx+19h], 2
0x1800549d0  jb      short loc_1800549E7
0x1800549d2  mov     rcx, [rcx+10h]
0x1800549d6  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x1800549dd  mov     edx, 48h ; 'H'
0x1800549e2  call    WPP_SF_
0x1800549e7  cmp     dword ptr [rsi+2C0h], 0
0x1800549ee  jz      short loc_180054A4A
0x1800549f0  mov     rcx, [r14]; String1
0x1800549f3  lea     r9, [rsp+2DC0h+hKey]
0x1800549f8  mov     rdx, r15; wchar_t *
0x1800549fb  mov     dword ptr [rsp+2DC0h+hKey], 0
0x180054a03  call    IsActiveAutoTriggerConnectionInternal
0x180054a08  cmp     dword ptr [rsp+2DC0h+hKey], 0
0x180054a0d  jz      short loc_180054A48
0x180054a0f  call    RasSelectNextTriggerProfile
0x180054a14  test    eax, eax
0x180054a16  jz      short loc_180054A48
0x180054a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a1f  cmp     rcx, rdi
0x180054a22  jz      short loc_180054A48
0x180054a24  test    [rcx+1Ch], r13d
0x180054a28  jz      short loc_180054A48
0x180054a2a  cmp     byte ptr [rcx+19h], 2
0x180054a2e  jb      short loc_180054A48
0x180054a30  mov     rcx, [rcx+10h]
0x180054a34  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180054a3b  mov     edx, 49h ; 'I'
0x180054a40  mov     r9d, eax
0x180054a43  call    WPP_SF_d
0x180054a48  xor     ebx, ebx
0x180054a4a  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x180054a51  call    cs:__imp_LeaveCriticalSection
0x180054a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a5e  cmp     rcx, rdi
0x180054a61  jz      short loc_180054A87
0x180054a63  test    [rcx+1Ch], r13d
0x180054a67  jz      short loc_180054A87
0x180054a69  cmp     byte ptr [rcx+19h], 6
0x180054a6d  jb      short loc_180054A87
0x180054a6f  mov     rcx, [rcx+10h]
0x180054a73  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180054a7a  mov     edx, 4Ah ; 'J'
0x180054a7f  mov     r9d, ebx
0x180054a82  call    WPP_SF_d
0x180054a87  mov     eax, ebx
0x180054a89  mov     rcx, [rbp+2CC0h+var_40]
0x180054a90  xor     rcx, rsp; StackCookie
0x180054a93  call    __security_check_cookie
0x180054a98  add     rsp, 2D90h
0x180054a9f  pop     r15
0x180054aa1  pop     r14
0x180054aa3  pop     r13
0x180054aa5  pop     rdi
0x180054aa6  pop     rsi
0x180054aa7  pop     rbx
0x180054aa8  pop     rbp
0x180054aa9  retn
```
