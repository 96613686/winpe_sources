# CiLogQueryDynamicCodeTrust

- ea: `0x18006d3cc`
- end: `0x18006d739`
- name: `CiLogQueryDynamicCodeTrust`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075684`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18006d3cc`
- `0x18006ea14`
- `0x18008f038`
- `0x18008f2d0`
- `0x180090564`
- `0x1800a3d3c`
- `0x1800a4678`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18006d4cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x18006d4cd`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d604`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d604`
- `ntoskrnl!EtwWrite` at `0x18006d726`
- `ntoskrnl!EtwWrite` at `0x18006d726`

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
0x18006d3cc  mov     [rsp-8+arg_0], rbx
0x18006d3d1  push    rbp
0x18006d3d2  push    rsi
0x18006d3d3  push    rdi
0x18006d3d4  push    r12
0x18006d3d6  push    r13
0x18006d3d8  push    r14
0x18006d3da  push    r15
0x18006d3dc  lea     rbp, [rsp-130h]
0x18006d3e4  sub     rsp, 230h
0x18006d3eb  mov     rax, cs:__security_cookie
0x18006d3f2  xor     rax, rsp
0x18006d3f5  mov     [rbp+160h+var_40], rax
0x18006d3fc  xor     r12d, r12d
0x18006d3ff  mov     r14, r8
0x18006d402  mov     rdi, rdx
0x18006d405  mov     [rbp+160h+var_1E0], r12
0x18006d409  mov     r15b, cl
0x18006d40c  mov     [rsp+260h+var_210], r12w
0x18006d412  xorps   xmm0, xmm0
0x18006d415  lea     rcx, [rbp+160h+var_80]; void *
0x18006d41c  lea     ebx, [r12+40h]
0x18006d421  xor     edx, edx; Val
0x18006d423  mov     r8d, ebx; Size
0x18006d426  mov     esi, r9d
0x18006d429  movups  [rsp+260h+var_1F8], xmm0
0x18006d42e  call    memset
0x18006d433  mov     r8d, ebx; Size
0x18006d436  mov     [rsp+260h+var_200], ebx
0x18006d43a  xor     edx, edx; Val
0x18006d43c  lea     rcx, [rbp+160h+var_100]; void *
0x18006d440  call    memset
0x18006d445  mov     r8d, ebx; Size
0x18006d448  mov     [rsp+260h+var_208], ebx
0x18006d44c  xor     edx, edx; Val
0x18006d44e  lea     rcx, [rbp+160h+var_C0]; void *
0x18006d455  call    memset
0x18006d45a  xor     eax, eax
0x18006d45c  mov     [rsp+260h+var_204], ebx
0x18006d460  mov     [rbp+160h+var_1C0], rax
0x18006d464  xorps   xmm0, xmm0
0x18006d467  mov     [rsp+260h+var_1E8], r12
0x18006d46c  mov     [rsp+260h+var_20C], r12w
0x18006d472  movups  [rbp+160h+var_1D8], xmm0
0x18006d476  test    r14, r14
0x18006d479  jnz     short loc_18006D4C9
0x18006d47b  test    esi, esi
0x18006d47d  jnz     short loc_18006D484
0x18006d47f  test    rdi, rdi
0x18006d482  jnz     short loc_18006D4CD
0x18006d484  mov     ebx, 0C000000Dh
0x18006d489  mov     rcx, [rsp+260h+var_1E8]
0x18006d48e  call    CipReleaseProcessName
0x18006d493  mov     rcx, [rbp+160h+var_1E0]
0x18006d497  call    CipReleaseFileName
0x18006d49c  mov     eax, ebx
0x18006d49e  mov     rcx, [rbp+160h+var_40]
0x18006d4a5  xor     rcx, rsp; StackCookie
0x18006d4a8  call    __security_check_cookie
0x18006d4ad  mov     rbx, [rsp+260h+arg_0]
0x18006d4b5  add     rsp, 230h
0x18006d4bc  pop     r15
0x18006d4be  pop     r14
0x18006d4c0  pop     r13
0x18006d4c2  pop     r12
0x18006d4c4  pop     rdi
0x18006d4c5  pop     rsi
0x18006d4c6  pop     rbp
0x18006d4c7  retn
0x18006d4c9  test    esi, esi
0x18006d4cb  jz      short loc_18006D484
0x18006d4cd  call    cs:__imp_PsGetCurrentProcess
0x18006d4d4  nop     dword ptr [rax+rax+00h]
0x18006d4d9  mov     rcx, rax
0x18006d4dc  lea     r8, [rsp+260h+var_1E8]
0x18006d4e1  lea     rdx, [rbp+160h+var_1D8]
0x18006d4e5  call    CipQueryProcessName
0x18006d4ea  test    rdi, rdi
0x18006d4ed  jz      short loc_18006D502
0x18006d4ef  lea     r8, [rbp+160h+var_1E0]
0x18006d4f3  mov     rcx, rdi
0x18006d4f6  lea     rdx, [rsp+260h+var_1F8]
0x18006d4fb  call    CipQueryFileName
0x18006d500  jmp     short loc_18006D550
0x18006d502  mov     [rsp+260h+var_228], r12
0x18006d507  lea     rax, [rbp+160h+var_1C8]
0x18006d50b  mov     [rsp+260h+var_230], r12
0x18006d510  lea     r9, [rsp+260h+var_1F8]
0x18006d515  mov     [rsp+260h+var_238], r12
0x18006d51a  mov     r8b, 1
0x18006d51d  mov     edx, esi
0x18006d51f  mov     [rsp+260h+UserData], rax
0x18006d524  mov     rcx, r14
0x18006d527  mov     [rbp+160h+var_1C8], r12
0x18006d52b  call    SIPolicyGetOriginalFilenameAndVersionFromImage
0x18006d530  test    eax, eax
0x18006d532  jns     short loc_18006D550
0x18006d534  mov     rax, [rbp+160h+var_1C0]
0x18006d538  mov     dword ptr [rsp+260h+var_1F8+4], eax
0x18006d53c  lea     rax, aInMemoryPeFile; "In_Memory_PE_File"
0x18006d543  mov     qword ptr [rsp+260h+var_1F8+8], rax
0x18006d548  mov     dword ptr [rsp+260h+var_1F8], 240022h
0x18006d550  lea     rax, [rsp+260h+var_200]
0x18006d555  mov     r13d, 800Ch
0x18006d55b  mov     [rsp+260h+var_220], rax
0x18006d560  mov     r9d, esi
0x18006d563  lea     rax, [rbp+160h+var_80]
0x18006d56a  mov     r8, r14
0x18006d56d  mov     [rsp+260h+var_228], rax
0x18006d572  mov     rdx, rdi
0x18006d575  mov     dword ptr [rsp+260h+var_230], r13d
0x18006d57a  xor     ecx, ecx
0x18006d57c  mov     byte ptr [rsp+260h+var_238], 1
0x18006d581  call    CipGetEnterpriseUmciFileHash
0x18006d586  mov     ebx, eax
0x18006d588  test    eax, eax
0x18006d58a  js      loc_18006D489
0x18006d590  lea     rax, [rsp+260h+var_208]
0x18006d595  mov     r9d, esi
0x18006d598  mov     [rsp+260h+var_220], rax
0x18006d59d  mov     r8, r14
0x18006d5a0  lea     rax, [rbp+160h+var_100]
0x18006d5a4  mov     rdx, rdi
0x18006d5a7  mov     [rsp+260h+var_228], rax
0x18006d5ac  xor     ecx, ecx
0x18006d5ae  mov     dword ptr [rsp+260h+var_230], 8004h
0x18006d5b6  mov     byte ptr [rsp+260h+var_238], r12b
0x18006d5bb  call    CipGetEnterpriseUmciFileHash
0x18006d5c0  mov     ebx, eax
0x18006d5c2  test    eax, eax
0x18006d5c4  js      loc_18006D489
0x18006d5ca  lea     rax, [rsp+260h+var_204]
0x18006d5cf  mov     r9d, esi
0x18006d5d2  mov     [rsp+260h+var_220], rax
0x18006d5d7  mov     r8, r14
0x18006d5da  lea     rax, [rbp+160h+var_C0]
0x18006d5e1  mov     rdx, rdi
0x18006d5e4  mov     [rsp+260h+var_228], rax
0x18006d5e9  xor     ecx, ecx
0x18006d5eb  mov     dword ptr [rsp+260h+var_230], r13d
0x18006d5f0  mov     byte ptr [rsp+260h+var_238], r12b
0x18006d5f5  call    CipGetEnterpriseUmciFileHash
0x18006d5fa  mov     ebx, eax
0x18006d5fc  test    eax, eax
0x18006d5fe  js      loc_18006D489
0x18006d604  call    cs:__imp_IoGetActivityIdThread
0x18006d60b  nop     dword ptr [rax+rax+00h]
0x18006d610  movzx   ecx, word ptr [rsp+260h+var_1F8]
0x18006d615  lea     rdx, CiDynamicCodeTrustAudited
0x18006d61c  mov     r8, rax; ActivityId
0x18006d61f  shr     cx, 1
0x18006d622  mov     [rsp+260h+var_210], cx
0x18006d627  lea     rax, [rsp+260h+var_210]
0x18006d62c  movzx   ecx, word ptr [rbp+160h+var_1D8]
0x18006d630  mov     r9d, 0Bh; UserDataCount
0x18006d636  mov     [rbp+160h+var_1B0.Ptr], rax
0x18006d63a  movzx   eax, word ptr [rsp+260h+var_1F8]
0x18006d63f  mov     [rbp+160h+var_198], eax
0x18006d642  lea     rax, [rsp+260h+var_20C]
0x18006d647  mov     [rbp+160h+var_190], rax
0x18006d64b  mov     rax, qword ptr [rbp+160h+var_1D8+8]
0x18006d64f  mov     [rbp+160h+var_180], rax
0x18006d653  movzx   eax, word ptr [rbp+160h+var_1D8]
0x18006d657  mov     [rbp+160h+var_178], eax
0x18006d65a  lea     rax, [rbp+160h+arg_20]
0x18006d661  mov     [rbp+160h+var_170], rax
0x18006d665  lea     rax, [rsp+260h+var_208]
0x18006d66a  mov     [rbp+160h+var_160], rax
0x18006d66e  lea     rax, [rbp+160h+var_100]
0x18006d672  mov     [rbp+160h+var_150], rax
0x18006d676  mov     eax, [rsp+260h+var_208]
0x18006d67a  mov     [rbp+160h+var_148], eax
0x18006d67d  lea     rax, [rsp+260h+var_204]
0x18006d682  mov     [rbp+160h+var_140], rax
0x18006d686  lea     rax, [rbp+160h+var_C0]
0x18006d68d  mov     [rbp+160h+var_130], rax
0x18006d691  mov     eax, [rsp+260h+var_204]
0x18006d695  mov     [rbp+160h+var_128], eax
0x18006d698  lea     rax, [rsp+260h+var_200]
0x18006d69d  mov     [rbp+160h+var_120], rax
0x18006d6a1  lea     rax, [rbp+160h+var_80]
0x18006d6a8  shr     cx, 1
0x18006d6ab  mov     [rbp+160h+var_110], rax
0x18006d6af  test    r15b, r15b
0x18006d6b2  mov     eax, [rsp+260h+var_200]
0x18006d6b6  mov     [rbp+160h+var_108], eax
0x18006d6b9  lea     rax, CiDynamicCodeTrustFailed
0x18006d6c0  mov     [rsp+260h+var_20C], cx
0x18006d6c5  cmovz   rdx, rax; EventDescriptor
0x18006d6c9  mov     rcx, qword ptr [rsp+260h+var_1F8+8]
0x18006d6ce  lea     rax, [rbp+160h+var_1B0]
0x18006d6d2  mov     [rbp+160h+var_1A0], rcx
0x18006d6d6  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d6dd  mov     [rsp+260h+UserData], rax; UserData
0x18006d6e2  mov     qword ptr [rbp+160h+var_1B0.Size], 2
0x18006d6ea  mov     [rbp+160h+var_194], r12d
0x18006d6ee  mov     [rbp+160h+var_188], 2
0x18006d6f6  mov     [rbp+160h+var_174], r12d
0x18006d6fa  mov     [rbp+160h+var_168], 4
0x18006d702  mov     [rbp+160h+var_158], 4
0x18006d70a  mov     [rbp+160h+var_144], r12d
0x18006d70e  mov     [rbp+160h+var_138], 4
0x18006d716  mov     [rbp+160h+var_124], r12d
0x18006d71a  mov     [rbp+160h+var_118], 4
0x18006d722  mov     [rbp+160h+var_104], r12d
0x18006d726  call    cs:__imp_EtwWrite
0x18006d72d  nop     dword ptr [rax+rax+00h]
0x18006d732  mov     ebx, eax
0x18006d734  jmp     loc_18006D489
```
