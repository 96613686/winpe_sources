# AiFinish

- ea: `0x18001f160`
- end: `0x18001f377`
- name: `AiFinish`
- size: `535`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800205c0`
- `0x180020b80`
- `0x180021810`

## callees

- `0x18001c088`
- `0x18001f160`
- `0x18002a8a0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001f28d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001f2b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001f2cd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001f28d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001f2b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001f2cd`
- `RASAPI32!EnableOrDisableNetComponent` at `0x18001f31a`
- `RASAPI32!EnableOrDisableNetComponent` at `0x18001f32d`
- `RASAPI32!EnableOrDisableNetComponent` at `0x18001f31a`
- `RASAPI32!EnableOrDisableNetComponent` at `0x18001f32d`
- `RASAPI32!ChangeEntryType` at `0x18001f1c4`
- `RASAPI32!ChangeEntryType` at `0x18001f1c4`
- `rtutils!TracePrintfExA` at `0x18001f189`
- `rtutils!TracePrintfExA` at `0x18001f189`

## pseudocode

```c
__int64 __fastcall AiFinish(HWND a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  __int64 result; // rax
  __int64 v5; // rbx
  __int64 i; // rsi
  __int64 v7; // rcx
  int v8; // eax
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rcx

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "AiFinish");
  v2 = AiContext(a1);
  v3 = v2;
  if ( !v2 )
    return 1003;
  v5 = *(_QWORD *)(*v2 + 872LL);
  ChangeEntryType(v5, *(unsigned int *)(*(_QWORD *)(**(_QWORD **)(v5 + 32) + 16LL) + 44LL));
  if ( *(_DWORD *)(v5 + 40) )
  {
    CopyPszListToPhoneList(*(_QWORD *)(*(_QWORD *)(*v3 + 328LL) + 16LL), v3[58]);
  }
  else
  {
    for ( i = **(_QWORD **)(v5 + 32); i; i = *(_QWORD *)(i + 8) )
    {
      v7 = *(_QWORD *)(i + 16);
      if ( *(_DWORD *)(v7 + 188) )
        CopyPszListToPhoneList(v7, v3[58]);
    }
  }
  *(_DWORD *)(v5 + 164) = *((_DWORD *)v3 + 120) != 0 ? 552 : 544;
  if ( *((_DWORD *)v3 + 153) == 7 )
    *(_DWORD *)(v5 + 164) = 2048;
  v8 = *((_DWORD *)v3 + 153);
  if ( !v8 || v8 == 7 )
    *(_DWORD *)(v5 + 492) = 15;
  if ( !*((_DWORD *)v3 + 128) && !*((_DWORD *)v3 + 119) )
    *(_DWORD *)(v5 + 236) |= 4u;
  v9 = *(const WCHAR **)(v5 + 280);
  if ( v9 && lstrcmpW(v9, L"0.0.0.0") )
    *(_DWORD *)(v5 + 320) = 2;
  v10 = *(const WCHAR **)(v5 + 288);
  if ( v10 && lstrcmpW(v10, L"0.0.0.0") || (v11 = *(const WCHAR **)(v5 + 304)) != 0 && lstrcmpW(v11, L"0.0.0.0") )
    *(_DWORD *)(v5 + 324) = 2;
  if ( *(_DWORD *)(v5 + 24) == 2 )
    *(_DWORD *)(v5 + 168) = *((_DWORD *)v3 + 153);
  *(_DWORD *)(v5 + 156) = 300;
  *(_DWORD *)(v5 + 328) = 0;
  *(_QWORD *)(v5 + 256) = 0;
  EnableOrDisableNetComponent(v5, L"ms_server", 0);
  EnableOrDisableNetComponent(v5, L"ms_msclient", 0);
  *(_DWORD *)(v5 + 332) = 0;
  result = 1;
  if ( !*(_DWORD *)(*v3 + 56LL) )
    *(_DWORD *)(*v3 + 24LL) = 1;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*v3 + 16LL) + 544LL) + 80LL) = v3[78];
  return result;
}

```

## disassembly

```asm
0x18001f160  mov     [rsp+arg_0], rbx
0x18001f165  mov     [rsp+arg_8], rsi
0x18001f16a  push    rdi
0x18001f16b  sub     rsp, 20h
0x18001f16f  mov     rbx, rcx
0x18001f172  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f178  cmp     ecx, 0FFFFFFFFh
0x18001f17b  jz      short loc_18001F18F
0x18001f17d  lea     r8, aAifinish; "AiFinish"
0x18001f184  mov     edx, 0Ch; dwFlags
0x18001f189  call    cs:__imp_TracePrintfExA
0x18001f18f  mov     rcx, rbx
0x18001f192  call    AiContext
0x18001f197  mov     rdi, rax
0x18001f19a  test    rax, rax
0x18001f19d  jnz     short loc_18001F1A9
0x18001f19f  mov     eax, 3EBh
0x18001f1a4  jmp     loc_18001F367
0x18001f1a9  mov     rax, [rax]
0x18001f1ac  mov     rbx, [rax+368h]
0x18001f1b3  mov     rax, [rbx+20h]
0x18001f1b7  mov     rcx, [rax]
0x18001f1ba  mov     rdx, [rcx+10h]
0x18001f1be  mov     rcx, rbx
0x18001f1c1  mov     edx, [rdx+2Ch]
0x18001f1c4  call    cs:__imp_ChangeEntryType
0x18001f1ca  cmp     dword ptr [rbx+28h], 0
0x18001f1ce  jz      short loc_18001F1EC
0x18001f1d0  mov     rax, [rdi]
0x18001f1d3  mov     rdx, [rdi+1D0h]
0x18001f1da  mov     rcx, [rax+148h]
0x18001f1e1  mov     rcx, [rcx+10h]
0x18001f1e5  call    CopyPszListToPhoneList
0x18001f1ea  jmp     short loc_18001F217
0x18001f1ec  mov     rax, [rbx+20h]
0x18001f1f0  mov     rsi, [rax]
0x18001f1f3  jmp     short loc_18001F212
0x18001f1f5  mov     rcx, [rsi+10h]
0x18001f1f9  cmp     dword ptr [rcx+0BCh], 0
0x18001f200  jz      short loc_18001F20E
0x18001f202  mov     rdx, [rdi+1D0h]
0x18001f209  call    CopyPszListToPhoneList
0x18001f20e  mov     rsi, [rsi+8]
0x18001f212  test    rsi, rsi
0x18001f215  jnz     short loc_18001F1F5
0x18001f217  mov     eax, [rdi+1E0h]
0x18001f21d  neg     eax
0x18001f21f  sbb     ecx, ecx
0x18001f221  and     ecx, 8
0x18001f224  add     ecx, 220h
0x18001f22a  mov     [rbx+0A4h], ecx
0x18001f230  cmp     dword ptr [rdi+264h], 7
0x18001f237  jnz     short loc_18001F243
0x18001f239  mov     dword ptr [rbx+0A4h], 800h
0x18001f243  mov     eax, [rdi+264h]
0x18001f249  test    eax, eax
0x18001f24b  jz      short loc_18001F252
0x18001f24d  cmp     eax, 7
0x18001f250  jnz     short loc_18001F25C
0x18001f252  mov     dword ptr [rbx+1ECh], 0Fh
0x18001f25c  cmp     dword ptr [rdi+200h], 0
0x18001f263  jnz     short loc_18001F275
0x18001f265  cmp     dword ptr [rdi+1DCh], 0
0x18001f26c  jnz     short loc_18001F275
0x18001f26e  or      dword ptr [rbx+0ECh], 4
0x18001f275  mov     rcx, [rbx+118h]; lpString1
0x18001f27c  mov     esi, 2
0x18001f281  test    rcx, rcx
0x18001f284  jz      short loc_18001F29D
0x18001f286  lea     rdx, a0000; "0.0.0.0"
0x18001f28d  call    cs:__imp_lstrcmpW
0x18001f293  test    eax, eax
0x18001f295  jz      short loc_18001F29D
0x18001f297  mov     [rbx+140h], esi
0x18001f29d  mov     rcx, [rbx+120h]; lpString1
0x18001f2a4  test    rcx, rcx
0x18001f2a7  jz      short loc_18001F2BA
0x18001f2a9  lea     rdx, a0000; "0.0.0.0"
0x18001f2b0  call    cs:__imp_lstrcmpW
0x18001f2b6  test    eax, eax
0x18001f2b8  jnz     short loc_18001F2D7
0x18001f2ba  mov     rcx, [rbx+130h]; lpString1
0x18001f2c1  test    rcx, rcx
0x18001f2c4  jz      short loc_18001F2DD
0x18001f2c6  lea     rdx, a0000; "0.0.0.0"
0x18001f2cd  call    cs:__imp_lstrcmpW
0x18001f2d3  test    eax, eax
0x18001f2d5  jz      short loc_18001F2DD
0x18001f2d7  mov     [rbx+144h], esi
0x18001f2dd  cmp     [rbx+18h], esi
0x18001f2e0  jnz     short loc_18001F2EE
0x18001f2e2  mov     eax, [rdi+264h]
0x18001f2e8  mov     [rbx+0A8h], eax
0x18001f2ee  xor     r8d, r8d
0x18001f2f1  mov     dword ptr [rbx+9Ch], 12Ch
0x18001f2fb  lea     rdx, aMsServer; "ms_server"
0x18001f302  mov     dword ptr [rbx+148h], 0
0x18001f30c  mov     rcx, rbx
0x18001f30f  mov     qword ptr [rbx+100h], 0
0x18001f31a  call    cs:__imp_EnableOrDisableNetComponent
0x18001f320  xor     r8d, r8d
0x18001f323  lea     rdx, String1; "ms_msclient"
0x18001f32a  mov     rcx, rbx
0x18001f32d  call    cs:__imp_EnableOrDisableNetComponent
0x18001f333  mov     dword ptr [rbx+14Ch], 0
0x18001f33d  mov     eax, 1
0x18001f342  mov     rcx, [rdi]
0x18001f345  cmp     dword ptr [rcx+38h], 0
0x18001f349  jnz     short loc_18001F34E
0x18001f34b  mov     [rcx+18h], eax
0x18001f34e  mov     rcx, [rdi]
0x18001f351  mov     rdx, [rcx+10h]
0x18001f355  mov     rcx, [rdi+270h]
0x18001f35c  mov     r8, [rdx+220h]
0x18001f363  mov     [r8+50h], rcx
0x18001f367  mov     rbx, [rsp+28h+arg_0]
0x18001f36c  mov     rsi, [rsp+28h+arg_8]
0x18001f371  add     rsp, 20h
0x18001f375  pop     rdi
0x18001f376  retn
```
