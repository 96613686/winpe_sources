# EuCredentialsCommitRasIPSec

- ea: `0x1800134d0`
- end: `0x180013657`
- name: `EuCredentialsCommitRasIPSec`
- size: `391`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012b78`

## callees

- `0x1800134d0`
- `0x18003ce6c`
- `0x18003d184`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180013522`
- `rtutils!TracePrintfExA` at `0x18001359d`
- `rtutils!TracePrintfExA` at `0x1800135fe`
- `rtutils!TracePrintfExA` at `0x180013522`
- `rtutils!TracePrintfExA` at `0x18001359d`
- `rtutils!TracePrintfExA` at `0x1800135fe`

## string_xrefs

- `0x180013518`: `EuCredentialsCommitRasIPSec`
- `0x1800135f2`: `EuCredentialsCommitRasIPSec: RasSetCredentials=%d`

## pseudocode

```c
__int64 __fastcall EuCredentialsCommitRasIPSec(__int64 a1)
{
  DWORD v2; // edi
  __int64 v3; // rcx
  wchar_t *v4; // rax
  int v6; // [rsp+20h] [rbp-468h]
  _DWORD v7[2]; // [rsp+40h] [rbp-448h] BYREF
  _BYTE v8[514]; // [rsp+48h] [rbp-440h] BYREF
  wchar_t v9[275]; // [rsp+24Ah] [rbp-23Eh] BYREF

  v2 = 0;
  memset_0(v7, 0, 0x42Cu);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EuCredentialsCommitRasIPSec");
  if ( *(_DWORD *)(a1 + 1008) )
  {
    memset_0(v8, 0, 0x424u);
    v7[0] = 1068;
    v7[1] = 16;
    EncodePasswordW((__int16 *)(a1 + 1012));
    v2 = StringCchCopyWrapW(v9, 0x101u, (const wchar_t *)(a1 + 1012));
    EncodePasswordW((__int16 *)(a1 + 1012));
    if ( !v2 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasSetCredentials(p,TRUE)");
      v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _DWORD *, _QWORD))g_pRasSetCredentials)(
             **(_QWORD **)(a1 + 64),
             *(_QWORD *)(*(_QWORD *)(a1 + 872) + 8LL),
             v7,
             0);
      v3 = 514;
      v4 = v9;
      do
      {
        *(_BYTE *)v4 = 0;
        v4 = (wchar_t *)((char *)v4 + 1);
        --v3;
      }
      while ( v3 );
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "EuCredentialsCommitRasIPSec: RasSetCredentials=%d", v2);
      if ( v2 )
        ErrorDlgUtil(*(HWND *)(*(_QWORD *)(a1 + 16) + 4LL), 0x13Bu, v2, 0, v6, 0x169u, 0xFAu);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800134d0  mov     [rsp+arg_8], rbx
0x1800134d5  mov     [rsp+arg_10], rsi
0x1800134da  push    rdi
0x1800134db  sub     rsp, 480h
0x1800134e2  mov     rax, cs:__security_cookie
0x1800134e9  xor     rax, rsp
0x1800134ec  mov     [rsp+488h+var_18], rax
0x1800134f4  mov     rsi, rcx
0x1800134f7  mov     ebx, 42Ch
0x1800134fc  mov     r8d, ebx; Size
0x1800134ff  lea     rcx, [rsp+488h+var_448]; void *
0x180013504  xor     edx, edx; Val
0x180013506  xor     edi, edi
0x180013508  call    memset_0
0x18001350d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180013513  cmp     ecx, 0FFFFFFFFh
0x180013516  jz      short loc_180013528
0x180013518  lea     r8, aEucredentialsc_2; "EuCredentialsCommitRasIPSec"
0x18001351f  lea     edx, [rdi+0Ch]; dwFlags
0x180013522  call    cs:__imp_TracePrintfExA
0x180013528  cmp     [rsi+3F0h], edi
0x18001352e  jz      loc_180013630
0x180013534  xor     edx, edx; Val
0x180013536  lea     rcx, [rsp+488h+var_440]; void *
0x18001353b  mov     r8d, 424h; Size
0x180013541  call    memset_0
0x180013546  mov     [rsp+488h+var_448], ebx
0x18001354a  lea     rbx, [rsi+3F4h]
0x180013551  mov     rcx, rbx
0x180013554  mov     [rsp+488h+var_444], 10h
0x18001355c  call    EncodePasswordW
0x180013561  mov     r8, rbx
0x180013564  lea     rcx, [rsp+488h+var_23E]
0x18001356c  mov     edx, 101h
0x180013571  call    StringCchCopyWrapW
0x180013576  mov     rcx, rbx
0x180013579  mov     edi, eax
0x18001357b  call    EncodePasswordW
0x180013580  test    edi, edi
0x180013582  jnz     loc_180013630
0x180013588  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001358e  cmp     ecx, 0FFFFFFFFh
0x180013591  jz      short loc_1800135A3
0x180013593  lea     r8, aRassetcredenti_0; "RasSetCredentials(p,TRUE)"
0x18001359a  lea     edx, [rdi+0Ch]; dwFlags
0x18001359d  call    cs:__imp_TracePrintfExA
0x1800135a3  mov     rdx, [rsi+368h]
0x1800135aa  lea     r8, [rsp+488h+var_448]
0x1800135af  mov     rcx, [rsi+40h]
0x1800135b3  xor     r9d, r9d
0x1800135b6  mov     rax, cs:g_pRasSetCredentials
0x1800135bd  mov     rdx, [rdx+8]
0x1800135c1  mov     rcx, [rcx]
0x1800135c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135c9  mov     edi, eax
0x1800135cb  mov     ecx, 202h
0x1800135d0  lea     rax, [rsp+488h+var_23E]
0x1800135d8  mov     byte ptr [rax], 0
0x1800135db  inc     rax
0x1800135de  sub     rcx, 1
0x1800135e2  jnz     short loc_1800135D8
0x1800135e4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800135ea  cmp     ecx, 0FFFFFFFFh
0x1800135ed  jz      short loc_180013604
0x1800135ef  mov     r9d, edi
0x1800135f2  lea     r8, aEucredentialsc_0; "EuCredentialsCommitRasIPSec: RasSetCred"...
0x1800135f9  mov     edx, 0Ch; dwFlags
0x1800135fe  call    cs:__imp_TracePrintfExA
0x180013604  test    edi, edi
0x180013606  jz      short loc_180013630
0x180013608  mov     rcx, [rsi+10h]
0x18001360c  xor     r9d, r9d
0x18001360f  mov     [rsp+488h+var_458], 0FAh; UINT
0x180013617  mov     r8d, edi; dwMessageId
0x18001361a  mov     edx, 13Bh; uID
0x18001361f  mov     [rsp+488h+var_460], 169h; UINT
0x180013627  mov     rcx, [rcx+4]; hWnd
0x18001362b  call    ErrorDlgUtil
0x180013630  mov     eax, edi
0x180013632  mov     rcx, [rsp+488h+var_18]
0x18001363a  xor     rcx, rsp; StackCookie
0x18001363d  call    __security_check_cookie
0x180013642  lea     r11, [rsp+488h+var_8]
0x18001364a  mov     rbx, [r11+18h]
0x18001364e  mov     rsi, [r11+20h]
0x180013652  mov     rsp, r11
0x180013655  pop     rdi
0x180013656  retn
```
