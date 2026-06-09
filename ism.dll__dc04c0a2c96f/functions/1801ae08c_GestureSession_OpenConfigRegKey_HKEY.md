# GestureSession::OpenConfigRegKey(HKEY__ * *)

- ea: `0x1801ae08c`
- end: `0x1801ae222`
- name: `?OpenConfigRegKey@GestureSession@@SAJPEAPEAUHKEY__@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801b0904`

## callees

- `0x1800f08d8`
- `0x1800f0990`
- `0x1801ae08c`
- `0x1801ae394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801ae169`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801ae1ae`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801ae169`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801ae1ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801ae132`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801ae17e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801ae132`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801ae17e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ae1d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ae1f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ae1d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ae1f3`

## pseudocode

```c
__int64 __fastcall GestureSession::OpenConfigRegKey(PHKEY phkResult)
{
  __int64 result; // rax
  __int64 v3; // rbx
  __int64 v4; // rax
  WCHAR SubKey[31]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v6[466]; // [rsp+6Eh] [rbp-92h] BYREF

  if ( GestureSession::s_refreshScreenSize )
  {
    result = GestureSession::RefreshScreenSize();
    if ( (int)result < 0 )
      return result;
    GestureSession::s_refreshScreenSize = 0;
  }
  wcscpy(SubKey, L"Software\\Microsoft\\Shel\\Input");
  memset_0(v6, 0, 0x1CAu);
  _o_wcscat_s(SubKey, 260, L"\\");
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( SubKey[v4] );
  _o__itow_s((unsigned int)GestureSession::s_horizontalResolution, &SubKey[v4], 260 - v4, 10);
  _o_wcscat_s(SubKey, 260, L"x");
  do
    ++v3;
  while ( SubKey[v3] );
  _o__itow_s((unsigned int)GestureSession::s_verticalResolution, &SubKey[v3], 260 - v3, 10);
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, phkResult);
  if ( !*phkResult )
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Shell\\Input", 0, 1u, phkResult);
  return 0;
}

```

## disassembly

```asm
0x1801ae08c  mov     [rsp-8+arg_8], rbx
0x1801ae091  mov     [rsp-8+arg_10], rsi
0x1801ae096  push    rbp
0x1801ae097  push    rdi
0x1801ae098  push    r14
0x1801ae09a  lea     rbp, [rsp-150h]
0x1801ae0a2  sub     rsp, 250h
0x1801ae0a9  mov     rax, cs:__security_cookie
0x1801ae0b0  xor     rax, rsp
0x1801ae0b3  mov     [rbp+160h+var_20], rax
0x1801ae0ba  xor     r14d, r14d
0x1801ae0bd  mov     rdi, rcx
0x1801ae0c0  cmp     cs:?s_refreshScreenSize@GestureSession@@0_NA, r14b; bool GestureSession::s_refreshScreenSize
0x1801ae0c7  jz      short loc_1801AE0DD
0x1801ae0c9  call    ?RefreshScreenSize@GestureSession@@SAJXZ; GestureSession::RefreshScreenSize(void)
0x1801ae0ce  test    eax, eax
0x1801ae0d0  js      loc_1801AE1FB
0x1801ae0d6  mov     cs:?s_refreshScreenSize@GestureSession@@0_NA, r14b; bool GestureSession::s_refreshScreenSize
0x1801ae0dd  movups  xmm0, xmmword ptr cs:aSoftwareMicros_0; "Software\\Microsoft\\Shell\\Input"
0x1801ae0e4  xor     edx, edx; Val
0x1801ae0e6  mov     r8d, 1CAh; Size
0x1801ae0ec  movups  xmm1, xmmword ptr cs:aSoftwareMicros_0+10h; "\\Microsoft\\Shell\\Input"
0x1801ae0f3  lea     rcx, [rsp+260h+var_1F2]; void *
0x1801ae0f8  movaps  xmmword ptr [rsp+260h+SubKey], xmm0
0x1801ae0fd  movups  xmm0, xmmword ptr cs:aSoftwareMicros_0+20h; "ft\\Shell\\Input"
0x1801ae104  movaps  [rsp+260h+var_220], xmm1
0x1801ae109  movups  xmm1, xmmword ptr cs:aSoftwareMicros_0+2Eh; "l\\Input"
0x1801ae110  movaps  [rsp+260h+var_210], xmm0
0x1801ae115  movups  [rsp+260h+var_210+0Eh], xmm1
0x1801ae11a  call    memset_0
0x1801ae11f  mov     esi, 104h
0x1801ae124  lea     r8, StringValue; "\\"
0x1801ae12b  mov     edx, esi
0x1801ae12d  lea     rcx, [rsp+260h+SubKey]
0x1801ae132  call    cs:__imp__o_wcscat_s
0x1801ae138  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801ae13c  lea     rcx, [rsp+260h+SubKey]
0x1801ae141  mov     rax, rbx
0x1801ae144  inc     rax
0x1801ae147  cmp     [rcx+rax*2], r14w
0x1801ae14c  jnz     short loc_1801AE144
0x1801ae14e  mov     ecx, cs:?s_horizontalResolution@GestureSession@@0HA; int GestureSession::s_horizontalResolution
0x1801ae154  lea     rdx, [rsp+260h+SubKey]
0x1801ae159  mov     r8, rsi
0x1801ae15c  lea     rdx, [rdx+rax*2]
0x1801ae160  sub     r8, rax
0x1801ae163  mov     r9d, 0Ah
0x1801ae169  call    cs:__imp__o__itow_s
0x1801ae16f  lea     r8, asc_1801FE610; "x"
0x1801ae176  mov     rdx, rsi
0x1801ae179  lea     rcx, [rsp+260h+SubKey]
0x1801ae17e  call    cs:__imp__o_wcscat_s
0x1801ae184  lea     rax, [rsp+260h+SubKey]
0x1801ae189  inc     rbx
0x1801ae18c  cmp     [rax+rbx*2], r14w
0x1801ae191  jnz     short loc_1801AE189
0x1801ae193  mov     ecx, cs:?s_verticalResolution@GestureSession@@0HA; int GestureSession::s_verticalResolution
0x1801ae199  lea     rdx, [rsp+260h+SubKey]
0x1801ae19e  sub     rsi, rbx
0x1801ae1a1  lea     rdx, [rdx+rbx*2]
0x1801ae1a5  mov     r8, rsi
0x1801ae1a8  mov     r9d, 0Ah
0x1801ae1ae  call    cs:__imp__o__itow_s
0x1801ae1b4  mov     ebx, 1
0x1801ae1b9  mov     [rsp+260h+phkResult], rdi; phkResult
0x1801ae1be  mov     rsi, 0FFFFFFFF80000002h
0x1801ae1c5  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1801ae1ca  mov     r9d, ebx; samDesired
0x1801ae1cd  mov     rcx, rsi; hKey
0x1801ae1d0  xor     r8d, r8d; ulOptions
0x1801ae1d3  call    cs:__imp_RegOpenKeyExW
0x1801ae1d9  cmp     [rdi], r14
0x1801ae1dc  jnz     short loc_1801AE1F9
0x1801ae1de  mov     r9d, ebx; samDesired
0x1801ae1e1  mov     [rsp+260h+phkResult], rdi; phkResult
0x1801ae1e6  xor     r8d, r8d; ulOptions
0x1801ae1e9  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Shell\\Input"
0x1801ae1f0  mov     rcx, rsi; hKey
0x1801ae1f3  call    cs:__imp_RegOpenKeyExW
0x1801ae1f9  xor     eax, eax
0x1801ae1fb  mov     rcx, [rbp+160h+var_20]
0x1801ae202  xor     rcx, rsp; StackCookie
0x1801ae205  call    __security_check_cookie
0x1801ae20a  lea     r11, [rsp+260h+var_10]
0x1801ae212  mov     rbx, [r11+28h]
0x1801ae216  mov     rsi, [r11+30h]
0x1801ae21a  mov     rsp, r11
0x1801ae21d  pop     r14
0x1801ae21f  pop     rdi
0x1801ae220  pop     rbp
0x1801ae221  retn
```
