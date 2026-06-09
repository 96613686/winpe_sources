# BthServLoadBackgroundBrokerModule(void)

- ea: `0x18000d218`
- end: `0x18000d491`
- name: `?BthServLoadBackgroundBrokerModule@@YAXXZ`
- size: `633`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e8f0`

## callees

- `0x18000d218`
- `0x180012004`
- `0x1800120b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d2b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d2b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d361`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fd`

## string_xrefs

- `0x18000d2a3`: `Windows.Internal.Devices.Bluetooth.dll`
- `0x18000d2cc`: `BthEvtBrCreateBroker`
- `0x18000d35a`: `BthEvtBrDeleteBroker`

## pseudocode

```c
void BthServLoadBackgroundBrokerModule(void)
{
  _BYTE *v0; // rcx
  char v1; // bl
  bool v2; // dl
  HMODULE Library; // rax
  bool v4; // di
  bool v5; // si
  int v6; // r8d
  int v7; // edx
  bool v8; // di
  bool v9; // si
  int v10; // r8d
  int v11; // edx

  v0 = WPP_GLOBAL_Control;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v0 = WPP_GLOBAL_Control;
  }
  if ( !hModule )
  {
    Library = LoadLibraryExW(L"Windows.Internal.Devices.Bluetooth.dll", 0, 0x800u);
    hModule = Library;
    if ( Library )
    {
      qword_180046FC0 = (__int64)GetProcAddress(Library, "BthEvtBrCreateBroker");
      if ( !qword_180046FC0 )
      {
        v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          GetLastError();
          LOBYTE(v6) = v5;
          LOBYTE(v7) = v4;
          WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v6, *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
      }
      qword_180046FC8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(hModule, "BthEvtBrDeleteBroker");
      if ( qword_180046FC8 )
        goto LABEL_33;
      v0 = WPP_GLOBAL_Control;
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_32:
        GetLastError();
        LOBYTE(v10) = v9;
        LOBYTE(v11) = v8;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10, *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_33:
        v0 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v0 = WPP_GLOBAL_Control;
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
    }
  }
  if ( v0 == (_BYTE *)&WPP_GLOBAL_Control || v0[25] < 5u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v0 + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v0 + 5));
}

```

## disassembly

```asm
0x18000d218  mov     [rsp+arg_0], rbx
0x18000d21d  mov     [rsp+arg_8], rbp
0x18000d222  mov     [rsp+arg_10], rsi
0x18000d227  push    rdi
0x18000d228  push    r14
0x18000d22a  push    r15
0x18000d22c  sub     rsp, 50h
0x18000d230  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d237  lea     rbp, WPP_GLOBAL_Control
0x18000d23e  mov     bl, 1
0x18000d240  cmp     rcx, rbp
0x18000d243  jz      short loc_18000D24F
0x18000d245  cmp     byte ptr [rcx+19h], 5
0x18000d249  jb      short loc_18000D24F
0x18000d24b  mov     dl, bl
0x18000d24d  jmp     short loc_18000D251
0x18000d24f  xor     dl, dl
0x18000d251  lea     r14, WPP_RECORDER_INITIALIZED
0x18000d258  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d25f  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d266  setnz   r8b
0x18000d26a  test    dl, dl
0x18000d26c  jnz     short loc_18000D273
0x18000d26e  test    r8b, r8b
0x18000d271  jz      short loc_18000D293
0x18000d273  mov     r9, [rcx+28h]
0x18000d277  mov     rcx, [rcx+10h]
0x18000d27b  mov     [rsp+68h+var_30], r15
0x18000d280  mov     [rsp+68h+var_38], 39h ; '9'
0x18000d287  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d28c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d293  cmp     cs:hModule, 0
0x18000d29b  jnz     loc_18000D43A
0x18000d2a1  xor     edx, edx; hFile
0x18000d2a3  lea     rcx, LibFileName; "Windows.Internal.Devices.Bluetooth.dll"
0x18000d2aa  mov     r8d, 800h; dwFlags
0x18000d2b0  call    cs:__imp_LoadLibraryExW
0x18000d2b7  nop     dword ptr [rax+rax+00h]
0x18000d2bc  mov     cs:hModule, rax
0x18000d2c3  test    rax, rax
0x18000d2c6  jz      loc_18000D3CE
0x18000d2cc  lea     rdx, aBthevtbrcreate; "BthEvtBrCreateBroker"
0x18000d2d3  mov     rcx, rax; hModule
0x18000d2d6  call    cs:__imp_GetProcAddress
0x18000d2dd  nop     dword ptr [rax+rax+00h]
0x18000d2e2  mov     cs:qword_180046FC0, rax
0x18000d2e9  test    rax, rax
0x18000d2ec  jnz     short loc_18000D353
0x18000d2ee  mov     rax, cs:WPP_GLOBAL_Control
0x18000d2f5  cmp     rax, rbp
0x18000d2f8  jz      short loc_18000D305
0x18000d2fa  cmp     byte ptr [rax+19h], 3
0x18000d2fe  jb      short loc_18000D305
0x18000d300  mov     dil, bl
0x18000d303  jmp     short loc_18000D308
0x18000d305  xor     dil, dil
0x18000d308  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d30f  setnz   sil
0x18000d313  test    dil, dil
0x18000d316  jnz     short loc_18000D31D
0x18000d318  test    sil, sil
0x18000d31b  jz      short loc_18000D353
0x18000d31d  call    cs:__imp_GetLastError
0x18000d324  nop     dword ptr [rax+rax+00h]
0x18000d329  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d330  mov     r8b, sil
0x18000d333  mov     [rsp+68h+var_20], eax
0x18000d337  mov     dl, dil
0x18000d33a  mov     [rsp+68h+var_30], r15
0x18000d33f  mov     [rsp+68h+var_38], 3Ah ; ':'
0x18000d346  mov     r9, [rcx+28h]
0x18000d34a  mov     rcx, [rcx+10h]
0x18000d34e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000d353  mov     rcx, cs:hModule; hModule
0x18000d35a  lea     rdx, aBthevtbrdelete; "BthEvtBrDeleteBroker"
0x18000d361  call    cs:__imp_GetProcAddress
0x18000d368  nop     dword ptr [rax+rax+00h]
0x18000d36d  mov     cs:qword_180046FC8, rax
0x18000d374  test    rax, rax
0x18000d377  jnz     loc_18000D433
0x18000d37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d384  cmp     rcx, rbp
0x18000d387  jz      short loc_18000D394
0x18000d389  cmp     byte ptr [rcx+19h], 3
0x18000d38d  jb      short loc_18000D394
0x18000d38f  mov     dil, bl
0x18000d392  jmp     short loc_18000D397
0x18000d394  xor     dil, dil
0x18000d397  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d39e  setnz   sil
0x18000d3a2  test    dil, dil
0x18000d3a5  jnz     short loc_18000D3B0
0x18000d3a7  test    sil, sil
0x18000d3aa  jz      loc_18000D43A
0x18000d3b0  call    cs:__imp_GetLastError
0x18000d3b7  nop     dword ptr [rax+rax+00h]
0x18000d3bc  mov     [rsp+68h+var_20], eax
0x18000d3c0  mov     [rsp+68h+var_30], r15
0x18000d3c5  mov     [rsp+68h+var_38], 3Bh ; ';'
0x18000d3cc  jmp     short loc_18000D419
0x18000d3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3d5  cmp     rcx, rbp
0x18000d3d8  jz      short loc_18000D3E5
0x18000d3da  cmp     byte ptr [rcx+19h], 3
0x18000d3de  jb      short loc_18000D3E5
0x18000d3e0  mov     dil, bl
0x18000d3e3  jmp     short loc_18000D3E8
0x18000d3e5  xor     dil, dil
0x18000d3e8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d3ef  setnz   sil
0x18000d3f3  test    dil, dil
0x18000d3f6  jnz     short loc_18000D3FD
0x18000d3f8  test    sil, sil
0x18000d3fb  jz      short loc_18000D43A
0x18000d3fd  call    cs:__imp_GetLastError
0x18000d404  nop     dword ptr [rax+rax+00h]
0x18000d409  mov     [rsp+68h+var_20], eax
0x18000d40d  mov     [rsp+68h+var_30], r15
0x18000d412  mov     [rsp+68h+var_38], 3Ch ; '<'
0x18000d419  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d420  mov     r8b, sil
0x18000d423  mov     dl, dil
0x18000d426  mov     r9, [rcx+28h]
0x18000d42a  mov     rcx, [rcx+10h]
0x18000d42e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000d433  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d43a  cmp     rcx, rbp
0x18000d43d  jz      short loc_18000D445
0x18000d43f  cmp     byte ptr [rcx+19h], 5
0x18000d443  jnb     short loc_18000D447
0x18000d445  xor     bl, bl
0x18000d447  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d44e  setnz   r8b
0x18000d452  test    bl, bl
0x18000d454  jnz     short loc_18000D45B
0x18000d456  test    r8b, r8b
0x18000d459  jz      short loc_18000D476
0x18000d45b  mov     r9, [rcx+28h]
0x18000d45f  mov     dl, bl
0x18000d461  mov     rcx, [rcx+10h]
0x18000d465  mov     [rsp+68h+var_30], r15
0x18000d46a  mov     [rsp+68h+var_38], 3Dh ; '='
0x18000d471  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d476  lea     r11, [rsp+68h+var_18]
0x18000d47b  mov     rbx, [r11+20h]
0x18000d47f  mov     rbp, [r11+28h]
0x18000d483  mov     rsi, [r11+30h]
0x18000d487  mov     rsp, r11
0x18000d48a  pop     r15
0x18000d48c  pop     r14
0x18000d48e  pop     rdi
0x18000d48f  retn
```
