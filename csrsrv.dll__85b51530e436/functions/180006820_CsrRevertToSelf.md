# CsrRevertToSelf

- ea: `0x180006820`
- end: `0x1800069d2`
- name: `CsrRevertToSelf`
- size: `434`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a270`

## callees

- `0x180006820`
- `0x180008d94`
- `0x18000ab61`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18000687b`
- `ntdll!NtSetInformationThread` at `0x18000687b`

## pseudocode

```c
bool CsrRevertToSelf()
{
  _DWORD *v0; // rax
  int v1; // ecx
  int v2; // ecx
  size_t v4; // rdx
  HRESULT v5; // eax
  char v6; // dl
  __int128 v7; // xmm1
  __int64 v8; // rcx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 ThreadInformation; // [rsp+20h] [rbp-F8h] BYREF
  char pszDest[16]; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v22; // [rsp+40h] [rbp-D8h]
  __int128 v23; // [rsp+50h] [rbp-C8h]
  __int128 v24; // [rsp+60h] [rbp-B8h]
  __int128 v25; // [rsp+70h] [rbp-A8h]
  __int128 v26; // [rsp+80h] [rbp-98h]
  __int128 v27; // [rsp+90h] [rbp-88h]
  __int128 v28; // [rsp+A0h] [rbp-78h]
  __int128 v29; // [rsp+B0h] [rbp-68h]
  __int128 v30; // [rsp+C0h] [rbp-58h]
  __int128 v31; // [rsp+D0h] [rbp-48h]
  _BYTE v32[28]; // [rsp+E0h] [rbp-38h]

  ThreadInformation = 0;
  v0 = KeGetPcr()->Unused1[1];
  if ( !v0 )
    goto LABEL_4;
  v1 = v0[20];
  if ( v1 )
  {
    v2 = v1 - 1;
    v0[20] = v2;
    if ( !v2 )
    {
LABEL_4:
      ThreadInformation = 0;
      return NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0;
    }
    return 1;
  }
  else
  {
    memset_0(pszDest, 0, 0xCCu);
    *(_DWORD *)&v32[24] = 2186;
    v5 = StringCbCopyA(pszDest, v4, "CsrRevertToSelf");
    if ( (int)(v5 + 0x80000000) >= 0 )
    {
      v6 = pszDest[0];
      if ( v5 != -2147024774 )
        v6 = 0;
      pszDest[0] = v6;
    }
    v7 = v22;
    v8 = 204LL * (_InterlockedIncrement(&dword_18000F024) % 16);
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 8] = *(_OWORD *)pszDest;
    v9 = v23;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 24] = v7;
    v10 = v24;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 40] = v9;
    v11 = v25;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 56] = v10;
    v12 = v26;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 72] = v11;
    v13 = v27;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 88] = v12;
    v14 = v28;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 104] = v13;
    v15 = v29;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 120] = v14;
    v16 = v30;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 136] = v15;
    v17 = v31;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 152] = v16;
    v18 = *(_OWORD *)v32;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 168] = v17;
    v19 = *(_OWORD *)&v32[12];
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 184] = v18;
    *(_OWORD *)&CsrpBlackboxBuffer[v8 + 196] = v19;
    return 0;
  }
}

```

## disassembly

```asm
0x180006820  push    rbx
0x180006822  sub     rsp, 110h
0x180006829  mov     rax, cs:__security_cookie
0x180006830  xor     rax, rsp
0x180006833  mov     [rsp+118h+var_18], rax
0x18000683b  xor     ebx, ebx
0x18000683d  mov     [rsp+118h+ThreadInformation], rbx
0x180006842  mov     rax, gs:70h
0x18000684b  test    rax, rax
0x18000684e  jz      short loc_18000685F
0x180006850  mov     ecx, [rax+50h]
0x180006853  test    ecx, ecx
0x180006855  jz      short loc_1800068AA
0x180006857  sub     ecx, 1
0x18000685a  mov     [rax+50h], ecx
0x18000685d  jnz     short loc_1800068A6
0x18000685f  mov     r9d, 8; ThreadInformationLength
0x180006865  mov     [rsp+118h+ThreadInformation], rbx
0x18000686a  lea     r8, [rsp+118h+ThreadInformation]; ThreadInformation
0x18000686f  mov     edx, 5; ThreadInformationClass
0x180006874  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000687b  call    cs:__imp_NtSetInformationThread
0x180006882  nop     dword ptr [rax+rax+00h]
0x180006887  shr     eax, 1Fh
0x18000688a  xor     al, 1
0x18000688c  mov     rcx, [rsp+118h+var_18]
0x180006894  xor     rcx, rsp; StackCookie
0x180006897  call    __security_check_cookie
0x18000689c  add     rsp, 110h
0x1800068a3  pop     rbx
0x1800068a4  retn
0x1800068a6  mov     al, 1
0x1800068a8  jmp     short loc_18000688C
0x1800068aa  xor     edx, edx; Val
0x1800068ac  lea     rcx, [rsp+118h+pszDest]; void *
0x1800068b1  mov     r8d, 0CCh; Size
0x1800068b7  call    memset_0
0x1800068bc  lea     r8, aCsrreverttosel_0; "CsrRevertToSelf"
0x1800068c3  mov     [rsp+118h+var_20], 88Ah
0x1800068ce  lea     rcx, [rsp+118h+pszDest]; pszDest
0x1800068d3  call    StringCbCopyA
0x1800068d8  mov     edx, 80000000h
0x1800068dd  lea     ecx, [rax+rdx]
0x1800068e0  test    edx, ecx
0x1800068e2  jnz     short loc_1800068F5
0x1800068e4  movzx   edx, [rsp+118h+pszDest]
0x1800068e9  cmp     eax, 8007007Ah
0x1800068ee  cmovnz  edx, ebx
0x1800068f1  mov     [rsp+118h+pszDest], dl
0x1800068f5  mov     eax, 1
0x1800068fa  lock xadd cs:dword_18000F024, eax
0x180006902  inc     eax
0x180006904  and     eax, 8000000Fh
0x180006909  jge     short loc_180006912
0x18000690b  dec     eax
0x18000690d  or      eax, 0FFFFFFF0h
0x180006910  inc     eax
0x180006912  movaps  xmm0, xmmword ptr [rsp+118h+pszDest]
0x180006917  movaps  xmm1, [rsp+118h+var_D8]
0x18000691c  cdqe
0x18000691e  imul    rcx, rax, 0CCh
0x180006925  lea     rax, CsrpBlackboxBuffer
0x18000692c  movups  xmmword ptr [rcx+rax+8], xmm0
0x180006931  movaps  xmm0, [rsp+118h+var_C8]
0x180006936  movups  xmmword ptr [rcx+rax+18h], xmm1
0x18000693b  movaps  xmm1, [rsp+118h+var_B8]
0x180006940  movups  xmmword ptr [rcx+rax+28h], xmm0
0x180006945  movaps  xmm0, [rsp+118h+var_A8]
0x18000694a  movups  xmmword ptr [rcx+rax+38h], xmm1
0x18000694f  movaps  xmm1, [rsp+118h+var_98]
0x180006957  movups  xmmword ptr [rcx+rax+48h], xmm0
0x18000695c  movaps  xmm0, [rsp+118h+var_88]
0x180006964  movups  xmmword ptr [rcx+rax+58h], xmm1
0x180006969  movaps  xmm1, [rsp+118h+var_78]
0x180006971  movups  xmmword ptr [rcx+rax+68h], xmm0
0x180006976  movaps  xmm0, [rsp+118h+var_68]
0x18000697e  movups  xmmword ptr [rcx+rax+78h], xmm1
0x180006983  movaps  xmm1, [rsp+118h+var_58]
0x18000698b  movups  xmmword ptr [rcx+rax+88h], xmm0
0x180006993  movaps  xmm0, [rsp+118h+var_48]
0x18000699b  movups  xmmword ptr [rcx+rax+98h], xmm1
0x1800069a3  movaps  xmm1, [rsp+118h+var_38]
0x1800069ab  movups  xmmword ptr [rcx+rax+0A8h], xmm0
0x1800069b3  movups  xmm0, [rsp+118h+var_38+0Ch]
0x1800069bb  movups  xmmword ptr [rcx+rax+0B8h], xmm1
0x1800069c3  movups  xmmword ptr [rcx+rax+0C4h], xmm0
0x1800069cb  xor     al, al
0x1800069cd  jmp     loc_18000688C
```
