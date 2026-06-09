# CiLogQueryDynamicCodeTrust

- ea: `0x18006c318`
- end: `0x18006c685`
- name: `CiLogQueryDynamicCodeTrust`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057120`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x18006c318`
- `0x18006d960`
- `0x18009dca8`
- `0x18009eac8`
- `0x18009ed60`
- `0x1800a2270`
- `0x1800a2ba8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18006c419`
- `ntoskrnl!PsGetCurrentProcess` at `0x18006c419`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c550`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c550`
- `ntoskrnl!EtwWrite` at `0x18006c672`
- `ntoskrnl!EtwWrite` at `0x18006c672`

## pseudocode

```c
__int64 __fastcall CiLogQueryDynamicCodeTrust(char a1, __int64 a2, __int64 a3, unsigned int a4, char a5)
{
  NTSTATUS EnterpriseUmciFileHash; // ebx
  __int64 CurrentProcess; // rax
  int v12; // r8d
  const GUID *ActivityIdThread; // rax
  const EVENT_DESCRIPTOR *v14; // rdx
  __int16 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v16; // [rsp+54h] [rbp-ACh] BYREF
  int v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+5Ch] [rbp-A4h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+98h] [rbp-68h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-40h]
  int v28; // [rsp+C8h] [rbp-38h]
  int v29; // [rsp+CCh] [rbp-34h]
  __int16 *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  __int64 v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+ECh] [rbp-14h]
  char *v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  int *v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  _BYTE *v39; // [rsp+110h] [rbp+10h]
  int v40; // [rsp+118h] [rbp+18h]
  int v41; // [rsp+11Ch] [rbp+1Ch]
  int *v42; // [rsp+120h] [rbp+20h]
  __int64 v43; // [rsp+128h] [rbp+28h]
  _BYTE *v44; // [rsp+130h] [rbp+30h]
  int v45; // [rsp+138h] [rbp+38h]
  int v46; // [rsp+13Ch] [rbp+3Ch]
  int *v47; // [rsp+140h] [rbp+40h]
  __int64 v48; // [rsp+148h] [rbp+48h]
  _BYTE *v49; // [rsp+150h] [rbp+50h]
  int v50; // [rsp+158h] [rbp+58h]
  int v51; // [rsp+15Ch] [rbp+5Ch]
  _BYTE v52[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v53[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v54[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  v22 = 0;
  v15 = 0;
  v20 = 0;
  memset(v54, 0, sizeof(v54));
  v19 = 64;
  memset(v52, 0, sizeof(v52));
  v17 = 64;
  memset(v53, 0, sizeof(v53));
  v18 = 64;
  v25 = 0;
  v21 = 0;
  v16 = 0;
  v23 = 0;
  if ( a3 )
  {
    if ( !a4 )
    {
LABEL_4:
      EnterpriseUmciFileHash = -1073741811;
      goto LABEL_5;
    }
  }
  else if ( a4 || !a2 )
  {
    goto LABEL_4;
  }
  CurrentProcess = PsGetCurrentProcess();
  CipQueryProcessName(CurrentProcess, &v23, &v21);
  if ( a2 )
  {
    CipQueryFileName(a2, &v20, &v22);
  }
  else
  {
    LOBYTE(v12) = 1;
    v24 = 0;
    if ( (int)SIPolicyGetOriginalFilenameAndVersionFromImage(a3, a4, v12, (unsigned int)&v20, (__int64)&v24, 0, 0, 0) < 0 )
    {
      DWORD1(v20) = v25;
      *((_QWORD *)&v20 + 1) = L"In_Memory_PE_File";
      LODWORD(v20) = 2359330;
    }
  }
  EnterpriseUmciFileHash = CipGetEnterpriseUmciFileHash(0, a2, a3, a4);
  if ( EnterpriseUmciFileHash >= 0 )
  {
    EnterpriseUmciFileHash = CipGetEnterpriseUmciFileHash(0, a2, a3, a4);
    if ( EnterpriseUmciFileHash >= 0 )
    {
      EnterpriseUmciFileHash = CipGetEnterpriseUmciFileHash(0, a2, a3, a4);
      if ( EnterpriseUmciFileHash >= 0 )
      {
        ActivityIdThread = (const GUID *)IoGetActivityIdThread();
        v14 = (const EVENT_DESCRIPTOR *)CiDynamicCodeTrustAudited;
        v15 = (unsigned __int16)v20 >> 1;
        UserData.Ptr = (ULONGLONG)&v15;
        v28 = (unsigned __int16)v20;
        v30 = &v16;
        v32 = *((_QWORD *)&v23 + 1);
        v33 = (unsigned __int16)v23;
        v35 = &a5;
        v37 = &v17;
        v39 = v52;
        v40 = v17;
        v42 = &v18;
        v44 = v53;
        v45 = v18;
        v47 = &v19;
        v49 = v54;
        v50 = v19;
        v16 = (unsigned __int16)v23 >> 1;
        if ( !a1 )
          v14 = &CiDynamicCodeTrustFailed;
        v27 = *((_QWORD *)&v20 + 1);
        *(_QWORD *)&UserData.Size = 2;
        v29 = 0;
        v31 = 2;
        v34 = 0;
        v36 = 4;
        v38 = 4;
        v41 = 0;
        v43 = 4;
        v46 = 0;
        v48 = 4;
        v51 = 0;
        EnterpriseUmciFileHash = EtwWrite(g_EtwEventHandle, v14, ActivityIdThread, 0xBu, &UserData);
      }
    }
  }
LABEL_5:
  CipReleaseProcessName(v21);
  CipReleaseFileName(v22);
  return (unsigned int)EnterpriseUmciFileHash;
}

```

## disassembly

```asm
0x18006c318  mov     [rsp-8+arg_0], rbx
0x18006c31d  push    rbp
0x18006c31e  push    rsi
0x18006c31f  push    rdi
0x18006c320  push    r12
0x18006c322  push    r13
0x18006c324  push    r14
0x18006c326  push    r15
0x18006c328  lea     rbp, [rsp-130h]
0x18006c330  sub     rsp, 230h
0x18006c337  mov     rax, cs:__security_cookie
0x18006c33e  xor     rax, rsp
0x18006c341  mov     [rbp+160h+var_40], rax
0x18006c348  xor     r12d, r12d
0x18006c34b  mov     r14, r8
0x18006c34e  mov     rdi, rdx
0x18006c351  mov     [rbp+160h+var_1E0], r12
0x18006c355  mov     r15b, cl
0x18006c358  mov     [rsp+260h+var_210], r12w
0x18006c35e  xorps   xmm0, xmm0
0x18006c361  lea     rcx, [rbp+160h+var_80]; void *
0x18006c368  lea     ebx, [r12+40h]
0x18006c36d  xor     edx, edx; Val
0x18006c36f  mov     r8d, ebx; Size
0x18006c372  mov     esi, r9d
0x18006c375  movups  [rsp+260h+var_1F8], xmm0
0x18006c37a  call    memset
0x18006c37f  mov     r8d, ebx; Size
0x18006c382  mov     [rsp+260h+var_200], ebx
0x18006c386  xor     edx, edx; Val
0x18006c388  lea     rcx, [rbp+160h+var_100]; void *
0x18006c38c  call    memset
0x18006c391  mov     r8d, ebx; Size
0x18006c394  mov     [rsp+260h+var_208], ebx
0x18006c398  xor     edx, edx; Val
0x18006c39a  lea     rcx, [rbp+160h+var_C0]; void *
0x18006c3a1  call    memset
0x18006c3a6  xor     eax, eax
0x18006c3a8  mov     [rsp+260h+var_204], ebx
0x18006c3ac  mov     [rbp+160h+var_1C0], rax
0x18006c3b0  xorps   xmm0, xmm0
0x18006c3b3  mov     [rsp+260h+var_1E8], r12
0x18006c3b8  mov     [rsp+260h+var_20C], r12w
0x18006c3be  movups  [rbp+160h+var_1D8], xmm0
0x18006c3c2  test    r14, r14
0x18006c3c5  jnz     short loc_18006C415
0x18006c3c7  test    esi, esi
0x18006c3c9  jnz     short loc_18006C3D0
0x18006c3cb  test    rdi, rdi
0x18006c3ce  jnz     short loc_18006C419
0x18006c3d0  mov     ebx, 0C000000Dh
0x18006c3d5  mov     rcx, [rsp+260h+var_1E8]
0x18006c3da  call    CipReleaseProcessName
0x18006c3df  mov     rcx, [rbp+160h+var_1E0]
0x18006c3e3  call    CipReleaseFileName
0x18006c3e8  mov     eax, ebx
0x18006c3ea  mov     rcx, [rbp+160h+var_40]
0x18006c3f1  xor     rcx, rsp; StackCookie
0x18006c3f4  call    __security_check_cookie
0x18006c3f9  mov     rbx, [rsp+260h+arg_0]
0x18006c401  add     rsp, 230h
0x18006c408  pop     r15
0x18006c40a  pop     r14
0x18006c40c  pop     r13
0x18006c40e  pop     r12
0x18006c410  pop     rdi
0x18006c411  pop     rsi
0x18006c412  pop     rbp
0x18006c413  retn
0x18006c415  test    esi, esi
0x18006c417  jz      short loc_18006C3D0
0x18006c419  call    cs:__imp_PsGetCurrentProcess
0x18006c420  nop     dword ptr [rax+rax+00h]
0x18006c425  mov     rcx, rax
0x18006c428  lea     r8, [rsp+260h+var_1E8]
0x18006c42d  lea     rdx, [rbp+160h+var_1D8]
0x18006c431  call    CipQueryProcessName
0x18006c436  test    rdi, rdi
0x18006c439  jz      short loc_18006C44E
0x18006c43b  lea     r8, [rbp+160h+var_1E0]
0x18006c43f  mov     rcx, rdi
0x18006c442  lea     rdx, [rsp+260h+var_1F8]
0x18006c447  call    CipQueryFileName
0x18006c44c  jmp     short loc_18006C49C
0x18006c44e  mov     [rsp+260h+var_228], r12
0x18006c453  lea     rax, [rbp+160h+var_1C8]
0x18006c457  mov     [rsp+260h+var_230], r12
0x18006c45c  lea     r9, [rsp+260h+var_1F8]
0x18006c461  mov     [rsp+260h+var_238], r12
0x18006c466  mov     r8b, 1
0x18006c469  mov     edx, esi
0x18006c46b  mov     [rsp+260h+UserData], rax
0x18006c470  mov     rcx, r14
0x18006c473  mov     [rbp+160h+var_1C8], r12
0x18006c477  call    SIPolicyGetOriginalFilenameAndVersionFromImage
0x18006c47c  test    eax, eax
0x18006c47e  jns     short loc_18006C49C
0x18006c480  mov     rax, [rbp+160h+var_1C0]
0x18006c484  mov     dword ptr [rsp+260h+var_1F8+4], eax
0x18006c488  lea     rax, aInMemoryPeFile; "In_Memory_PE_File"
0x18006c48f  mov     qword ptr [rsp+260h+var_1F8+8], rax
0x18006c494  mov     dword ptr [rsp+260h+var_1F8], 240022h
0x18006c49c  lea     rax, [rsp+260h+var_200]
0x18006c4a1  mov     r13d, 800Ch
0x18006c4a7  mov     [rsp+260h+var_220], rax
0x18006c4ac  mov     r9d, esi
0x18006c4af  lea     rax, [rbp+160h+var_80]
0x18006c4b6  mov     r8, r14
0x18006c4b9  mov     [rsp+260h+var_228], rax
0x18006c4be  mov     rdx, rdi
0x18006c4c1  mov     dword ptr [rsp+260h+var_230], r13d
0x18006c4c6  xor     ecx, ecx
0x18006c4c8  mov     byte ptr [rsp+260h+var_238], 1
0x18006c4cd  call    CipGetEnterpriseUmciFileHash
0x18006c4d2  mov     ebx, eax
0x18006c4d4  test    eax, eax
0x18006c4d6  js      loc_18006C3D5
0x18006c4dc  lea     rax, [rsp+260h+var_208]
0x18006c4e1  mov     r9d, esi
0x18006c4e4  mov     [rsp+260h+var_220], rax
0x18006c4e9  mov     r8, r14
0x18006c4ec  lea     rax, [rbp+160h+var_100]
0x18006c4f0  mov     rdx, rdi
0x18006c4f3  mov     [rsp+260h+var_228], rax
0x18006c4f8  xor     ecx, ecx
0x18006c4fa  mov     dword ptr [rsp+260h+var_230], 8004h
0x18006c502  mov     byte ptr [rsp+260h+var_238], r12b
0x18006c507  call    CipGetEnterpriseUmciFileHash
0x18006c50c  mov     ebx, eax
0x18006c50e  test    eax, eax
0x18006c510  js      loc_18006C3D5
0x18006c516  lea     rax, [rsp+260h+var_204]
0x18006c51b  mov     r9d, esi
0x18006c51e  mov     [rsp+260h+var_220], rax
0x18006c523  mov     r8, r14
0x18006c526  lea     rax, [rbp+160h+var_C0]
0x18006c52d  mov     rdx, rdi
0x18006c530  mov     [rsp+260h+var_228], rax
0x18006c535  xor     ecx, ecx
0x18006c537  mov     dword ptr [rsp+260h+var_230], r13d
0x18006c53c  mov     byte ptr [rsp+260h+var_238], r12b
0x18006c541  call    CipGetEnterpriseUmciFileHash
0x18006c546  mov     ebx, eax
0x18006c548  test    eax, eax
0x18006c54a  js      loc_18006C3D5
0x18006c550  call    cs:__imp_IoGetActivityIdThread
0x18006c557  nop     dword ptr [rax+rax+00h]
0x18006c55c  movzx   ecx, word ptr [rsp+260h+var_1F8]
0x18006c561  lea     rdx, CiDynamicCodeTrustAudited
0x18006c568  mov     r8, rax; ActivityId
0x18006c56b  shr     cx, 1
0x18006c56e  mov     [rsp+260h+var_210], cx
0x18006c573  lea     rax, [rsp+260h+var_210]
0x18006c578  movzx   ecx, word ptr [rbp+160h+var_1D8]
0x18006c57c  mov     r9d, 0Bh; UserDataCount
0x18006c582  mov     [rbp+160h+var_1B0.Ptr], rax
0x18006c586  movzx   eax, word ptr [rsp+260h+var_1F8]
0x18006c58b  mov     [rbp+160h+var_198], eax
0x18006c58e  lea     rax, [rsp+260h+var_20C]
0x18006c593  mov     [rbp+160h+var_190], rax
0x18006c597  mov     rax, qword ptr [rbp+160h+var_1D8+8]
0x18006c59b  mov     [rbp+160h+var_180], rax
0x18006c59f  movzx   eax, word ptr [rbp+160h+var_1D8]
0x18006c5a3  mov     [rbp+160h+var_178], eax
0x18006c5a6  lea     rax, [rbp+160h+arg_20]
0x18006c5ad  mov     [rbp+160h+var_170], rax
0x18006c5b1  lea     rax, [rsp+260h+var_208]
0x18006c5b6  mov     [rbp+160h+var_160], rax
0x18006c5ba  lea     rax, [rbp+160h+var_100]
0x18006c5be  mov     [rbp+160h+var_150], rax
0x18006c5c2  mov     eax, [rsp+260h+var_208]
0x18006c5c6  mov     [rbp+160h+var_148], eax
0x18006c5c9  lea     rax, [rsp+260h+var_204]
0x18006c5ce  mov     [rbp+160h+var_140], rax
0x18006c5d2  lea     rax, [rbp+160h+var_C0]
0x18006c5d9  mov     [rbp+160h+var_130], rax
0x18006c5dd  mov     eax, [rsp+260h+var_204]
0x18006c5e1  mov     [rbp+160h+var_128], eax
0x18006c5e4  lea     rax, [rsp+260h+var_200]
0x18006c5e9  mov     [rbp+160h+var_120], rax
0x18006c5ed  lea     rax, [rbp+160h+var_80]
0x18006c5f4  shr     cx, 1
0x18006c5f7  mov     [rbp+160h+var_110], rax
0x18006c5fb  test    r15b, r15b
0x18006c5fe  mov     eax, [rsp+260h+var_200]
0x18006c602  mov     [rbp+160h+var_108], eax
0x18006c605  lea     rax, CiDynamicCodeTrustFailed
0x18006c60c  mov     [rsp+260h+var_20C], cx
0x18006c611  cmovz   rdx, rax; EventDescriptor
0x18006c615  mov     rcx, qword ptr [rsp+260h+var_1F8+8]
0x18006c61a  lea     rax, [rbp+160h+var_1B0]
0x18006c61e  mov     [rbp+160h+var_1A0], rcx
0x18006c622  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c629  mov     [rsp+260h+UserData], rax; UserData
0x18006c62e  mov     qword ptr [rbp+160h+var_1B0.Size], 2
0x18006c636  mov     [rbp+160h+var_194], r12d
0x18006c63a  mov     [rbp+160h+var_188], 2
0x18006c642  mov     [rbp+160h+var_174], r12d
0x18006c646  mov     [rbp+160h+var_168], 4
0x18006c64e  mov     [rbp+160h+var_158], 4
0x18006c656  mov     [rbp+160h+var_144], r12d
0x18006c65a  mov     [rbp+160h+var_138], 4
0x18006c662  mov     [rbp+160h+var_124], r12d
0x18006c666  mov     [rbp+160h+var_118], 4
0x18006c66e  mov     [rbp+160h+var_104], r12d
0x18006c672  call    cs:__imp_EtwWrite
0x18006c679  nop     dword ptr [rax+rax+00h]
0x18006c67e  mov     ebx, eax
0x18006c680  jmp     loc_18006C3D5
```
