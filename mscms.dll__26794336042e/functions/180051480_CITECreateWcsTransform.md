# CITECreateWcsTransform

- ea: `0x180051480`
- end: `0x18005170e`
- name: `CITECreateWcsTransform`
- size: `654`
- prototype: `__int64 __usercall@<rax>(struct tagLOGCOLORSPACEW *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003cec4`

## callees

- `0x18000a740`
- `0x18000bce0`
- `0x18000fe30`
- `0x18002a6f8`
- `0x18002b058`
- `0x18002e5f0`
- `0x18005082c`
- `0x180051480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005169c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005169c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800516cb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800516cb`

## pseudocode

```c
__int64 __fastcall CITECreateWcsTransform(struct tagLOGCOLORSPACEW *a1, __int64 a2, __int64 a3, int a4, __int64 *a5)
{
  int v6; // r14d
  void *v7; // r15
  __int64 v8; // r13
  DWORD v9; // r12d
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD v12; // r9d
  __int64 v13; // rcx
  HRESULT v14; // eax
  signed int v15; // ebx
  unsigned int v16; // edi
  HPROFILE v17; // rax
  LCSGAMUTMATCH lcsIntent; // ecx
  int v19; // ecx
  int v20; // ecx
  signed int LastError; // eax
  signed int v22; // eax
  _BYTE v25[12]; // [rsp+44h] [rbp-4Dh] BYREF
  PROFILE pCDMPProfile; // [rsp+50h] [rbp-41h] BYREF
  __int64 v27; // [rsp+68h] [rbp-29h]
  __int64 v28; // [rsp+70h] [rbp-21h]
  __int64 *v29; // [rsp+78h] [rbp-19h]
  unsigned int v30; // [rsp+80h] [rbp-11h] BYREF
  int v31; // [rsp+84h] [rbp-Dh]
  int v32; // [rsp+88h] [rbp-9h]
  void *v33; // [rsp+90h] [rbp-1h] BYREF
  __int64 v34; // [rsp+98h] [rbp+7h]
  __int64 v35; // [rsp+A0h] [rbp+Fh]

  v27 = a2;
  v6 = 0;
  v29 = a5;
  v28 = a3;
  *(_DWORD *)&v25[8] = 0;
  v7 = 0;
  v8 = 0;
  memset(&pCDMPProfile, 0, sizeof(pCDMPProfile));
  v9 = 0;
  *(_QWORD *)v25 = (unsigned int)ValidHandle(a2, 1129860428);
  v12 = 1;
  if ( v11 && (unsigned int)ValidHandle(v11, v10) )
    v9 = v12;
  if ( a1->lcsFilename[0] )
  {
    pCDMPProfile.dwType = v12;
    v13 = -1;
    pCDMPProfile.pProfileData = a1->lcsFilename;
    pCDMPProfile.cbDataSize = 0;
    do
      ++v13;
    while ( a1->lcsFilename[v13] );
    v14 = ULongLongToULong(2 * v13 + 2, &pCDMPProfile.cbDataSize);
    v15 = (v14 >> 31) & 0x80070057;
    if ( v14 >> 31 == -1 )
      goto LABEL_39;
    goto LABEL_13;
  }
  if ( a1->lcsCSType )
  {
    v15 = -2147024809;
    goto LABEL_39;
  }
  if ( (unsigned int)InternalCreateProfileFromLCS(a1, (unsigned __int8 **)&v25[4], v12) && *(_QWORD *)&v25[4] )
  {
    pCDMPProfile.pProfileData = *(PVOID *)&v25[4];
    v15 = 0;
    pCDMPProfile.dwType = 2;
    pCDMPProfile.cbDataSize = _byteswap_ulong(**(_DWORD **)&v25[4]);
LABEL_13:
    v16 = 3;
    v17 = WcsOpenColorProfileW(&pCDMPProfile, 0, 0, 1u, 1u, 3u, 0);
    v7 = v17;
    if ( v17 && (unsigned int)ValidHandle(v17, 1129860428) )
      v6 = 1;
    if ( (a4 & 0x200000) != 0 || v6 || *(_DWORD *)v25 || v9 )
    {
      lcsIntent = a1->lcsIntent;
      v35 = 0;
      v30 = 1;
      v19 = lcsIntent - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
          v31 = v20 == 6 ? 3 : 0;
        else
          v31 = 1;
      }
      else
      {
        v31 = 2;
      }
      v33 = v7;
      if ( v28 )
      {
        v34 = v28;
        v35 = v27;
        v32 = 1;
      }
      else
      {
        v16 = 2;
        v34 = v27;
      }
      v8 = CITECreateMultiProfileTransform((__int64)&v33, v16, &v30, v16, a4);
      if ( !v8 )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    goto LABEL_39;
  }
  v22 = GetLastError();
  v15 = v22;
  if ( v22 > 0 )
    v15 = (unsigned __int16)v22 | 0x80070000;
  if ( v15 >= 0 )
    v15 = -2147024809;
LABEL_39:
  if ( *(_QWORD *)&v25[4] )
    GlobalFree(*(HGLOBAL *)&v25[4]);
  if ( v7 )
    CloseColorProfile(v7);
  *v29 = v8;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180051480  mov     [rsp-8+arg_8], rbx
0x180051485  push    rbp
0x180051486  push    rsi
0x180051487  push    rdi
0x180051488  push    r12
0x18005148a  push    r13
0x18005148c  push    r14
0x18005148e  push    r15
0x180051490  lea     rbp, [rsp-1Fh]
0x180051495  sub     rsp, 0B0h
0x18005149c  mov     rax, cs:__security_cookie
0x1800514a3  xor     rax, rsp
0x1800514a6  mov     [rbp+4Fh+var_38], rax
0x1800514aa  mov     rsi, rcx
0x1800514ad  mov     [rbp+4Fh+var_78], rdx
0x1800514b1  mov     rcx, [rbp+4Fh+arg_20]
0x1800514b5  xor     r14d, r14d
0x1800514b8  mov     [rbp+4Fh+var_68], rcx
0x1800514bc  mov     rax, rdx
0x1800514bf  xor     ecx, ecx
0x1800514c1  mov     [rbp+4Fh+var_A0], r9d
0x1800514c5  mov     qword ptr [rbp+4Fh+pCDMPProfile.cbDataSize], rcx
0x1800514c9  xorps   xmm0, xmm0
0x1800514cc  mov     rcx, rax
0x1800514cf  mov     [rbp+4Fh+var_70], r8
0x1800514d3  mov     edx, 43584D4Ch
0x1800514d8  mov     [rbp+4Fh+hMem], r14
0x1800514dc  mov     r15d, r14d
0x1800514df  mov     r13d, r14d
0x1800514e2  movups  xmmword ptr [rbp+4Fh+pCDMPProfile.dwType], xmm0
0x1800514e6  mov     r12d, r14d
0x1800514e9  call    ValidHandle
0x1800514ee  mov     [rbp+4Fh+var_9C], eax
0x1800514f1  lea     r9d, [r14+1]
0x1800514f5  test    r8, r8
0x1800514f8  jz      short loc_180051508
0x1800514fa  mov     rcx, r8
0x1800514fd  call    ValidHandle
0x180051502  test    eax, eax
0x180051504  cmovnz  r12d, r9d
0x180051508  lea     rax, [rsi+44h]
0x18005150c  cmp     [rax], r14w
0x180051510  jz      short loc_180051550
0x180051512  mov     [rbp+4Fh+pCDMPProfile.dwType], r9d
0x180051516  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005151a  mov     [rbp+4Fh+pCDMPProfile.pProfileData], rax
0x18005151e  mov     [rbp+4Fh+pCDMPProfile.cbDataSize], r14d
0x180051522  inc     rcx
0x180051525  cmp     [rax+rcx*2], r14w
0x18005152a  jnz     short loc_180051522
0x18005152c  lea     rcx, ds:2[rcx*2]; ullOperand
0x180051534  lea     rdx, [rbp+4Fh+pCDMPProfile.cbDataSize]; pulResult
0x180051538  call    ULongLongToULong
0x18005153d  mov     ebx, eax
0x18005153f  sar     ebx, 1Fh
0x180051542  and     ebx, 80070057h
0x180051548  jl      loc_1800516C2
0x18005154e  jmp     short loc_180051593
0x180051550  cmp     [rsi+0Ch], r14d
0x180051554  jnz     loc_1800516BD
0x18005155a  mov     r8d, r9d; int
0x18005155d  lea     rdx, [rbp+4Fh+hMem]; unsigned __int8 **
0x180051561  mov     rcx, rsi; struct tagLOGCOLORSPACEW *
0x180051564  call    ?InternalCreateProfileFromLCS@@YAHPEAUtagLOGCOLORSPACEW@@PEAPEAEH@Z; InternalCreateProfileFromLCS(tagLOGCOLORSPACEW *,uchar * *,int)
0x180051569  test    eax, eax
0x18005156b  jz      loc_18005169C
0x180051571  mov     rax, [rbp+4Fh+hMem]
0x180051575  test    rax, rax
0x180051578  jz      loc_18005169C
0x18005157e  mov     [rbp+4Fh+pCDMPProfile.pProfileData], rax
0x180051582  mov     ebx, r14d
0x180051585  mov     [rbp+4Fh+pCDMPProfile.dwType], 2
0x18005158c  mov     eax, [rax]
0x18005158e  bswap   eax
0x180051590  mov     [rbp+4Fh+pCDMPProfile.cbDataSize], eax
0x180051593  mov     edi, 3
0x180051598  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x18005159d  mov     [rsp+0E0h+dwCreationMode], edi; dwCreationMode
0x1800515a1  lea     rcx, [rbp+4Fh+pCDMPProfile]; pCDMPProfile
0x1800515a5  xor     r8d, r8d; pGMMPProfile
0x1800515a8  xor     edx, edx; pCAMPProfile
0x1800515aa  lea     r9d, [rdi-2]; dwDesireAccess
0x1800515ae  mov     [rsp+0E0h+dwShareMode], r9d; dwShareMode
0x1800515b3  call    WcsOpenColorProfileW
0x1800515b8  mov     r15, rax
0x1800515bb  test    rax, rax
0x1800515be  jz      short loc_1800515D9
0x1800515c0  mov     edx, 43584D4Ch
0x1800515c5  mov     rcx, rax
0x1800515c8  call    ValidHandle
0x1800515cd  test    eax, eax
0x1800515cf  lea     r8d, [rdi-2]
0x1800515d3  cmovnz  r14d, r8d
0x1800515d7  jmp     short loc_1800515DF
0x1800515d9  mov     r8d, 1
0x1800515df  mov     edx, [rbp+4Fh+var_A0]
0x1800515e2  bt      edx, 15h
0x1800515e6  jb      short loc_180051601
0x1800515e8  test    r14d, r14d
0x1800515eb  jnz     short loc_180051601
0x1800515ed  xor     r14d, r14d
0x1800515f0  cmp     [rbp+4Fh+var_9C], r14d
0x1800515f4  jnz     short loc_180051604
0x1800515f6  test    r12d, r12d
0x1800515f9  jz      loc_1800516C2
0x1800515ff  jmp     short loc_180051604
0x180051601  xor     r14d, r14d
0x180051604  mov     ecx, [rsi+10h]
0x180051607  mov     [rbp+4Fh+var_40], r14
0x18005160b  mov     [rbp+4Fh+var_60], r8d
0x18005160f  sub     ecx, 1
0x180051612  jz      short loc_180051634
0x180051614  sub     ecx, 1
0x180051617  jz      short loc_18005162E
0x180051619  sub     ecx, 2
0x18005161c  jz      short loc_180051628
0x18005161e  cmp     ecx, 4
0x180051621  jnz     short loc_180051628
0x180051623  mov     [rbp+4Fh+var_5C], edi
0x180051626  jmp     short loc_18005163B
0x180051628  mov     [rbp+4Fh+var_5C], r14d
0x18005162c  jmp     short loc_18005163B
0x18005162e  mov     [rbp+4Fh+var_5C], r8d
0x180051632  jmp     short loc_18005163B
0x180051634  mov     [rbp+4Fh+var_5C], 2
0x18005163b  mov     rax, [rbp+4Fh+var_70]
0x18005163f  mov     [rbp+4Fh+var_50], r15
0x180051643  test    rax, rax
0x180051646  jz      short loc_18005165A
0x180051648  mov     [rbp+4Fh+var_48], rax
0x18005164c  mov     rax, [rbp+4Fh+var_78]
0x180051650  mov     [rbp+4Fh+var_40], rax
0x180051654  mov     [rbp+4Fh+var_58], r8d
0x180051658  jmp     short loc_180051667
0x18005165a  mov     rax, [rbp+4Fh+var_78]
0x18005165e  mov     edi, 2
0x180051663  mov     [rbp+4Fh+var_48], rax
0x180051667  mov     [rsp+0E0h+dwShareMode], edx
0x18005166b  lea     r8, [rbp+4Fh+var_60]
0x18005166f  mov     edx, edi
0x180051671  lea     rcx, [rbp+4Fh+var_50]
0x180051675  mov     r9d, edi
0x180051678  call    CITECreateMultiProfileTransform
0x18005167d  mov     r13, rax
0x180051680  test    rax, rax
0x180051683  jnz     short loc_1800516C2
0x180051685  call    cs:__imp_GetLastError
0x18005168b  mov     ebx, eax
0x18005168d  test    eax, eax
0x18005168f  jle     short loc_1800516C2
0x180051691  movzx   ebx, ax
0x180051694  or      ebx, 80070000h
0x18005169a  jmp     short loc_1800516C2
0x18005169c  call    cs:__imp_GetLastError
0x1800516a2  mov     ebx, eax
0x1800516a4  test    eax, eax
0x1800516a6  jle     short loc_1800516B1
0x1800516a8  movzx   ebx, ax
0x1800516ab  or      ebx, 80070000h
0x1800516b1  test    ebx, ebx
0x1800516b3  mov     eax, 80070057h
0x1800516b8  cmovns  ebx, eax
0x1800516bb  jmp     short loc_1800516C2
0x1800516bd  mov     ebx, 80070057h
0x1800516c2  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800516c6  test    rcx, rcx
0x1800516c9  jz      short loc_1800516D1
0x1800516cb  call    cs:__imp_GlobalFree
0x1800516d1  test    r15, r15
0x1800516d4  jz      short loc_1800516DE
0x1800516d6  mov     rcx, r15; hProfile
0x1800516d9  call    CloseColorProfile
0x1800516de  mov     rax, [rbp+4Fh+var_68]
0x1800516e2  mov     [rax], r13
0x1800516e5  mov     eax, ebx
0x1800516e7  mov     rcx, [rbp+4Fh+var_38]
0x1800516eb  xor     rcx, rsp; StackCookie
0x1800516ee  call    __security_check_cookie
0x1800516f3  mov     rbx, [rsp+0E0h+arg_8]
0x1800516fb  add     rsp, 0B0h
0x180051702  pop     r15
0x180051704  pop     r14
0x180051706  pop     r13
0x180051708  pop     r12
0x18005170a  pop     rdi
0x18005170b  pop     rsi
0x18005170c  pop     rbp
0x18005170d  retn
```
