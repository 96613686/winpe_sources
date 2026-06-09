# CiLogQueryDynamicCodeTrust

- ea: `0x18006d0ec`
- end: `0x18006d459`
- name: `CiLogQueryDynamicCodeTrust`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800753a4`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18006d0ec`
- `0x18006e734`
- `0x18009f2d8`
- `0x1800a00f8`
- `0x1800a0390`
- `0x1800a38a0`
- `0x1800a41d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18006d1ed`
- `ntoskrnl!PsGetCurrentProcess` at `0x18006d1ed`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d324`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d324`
- `ntoskrnl!EtwWrite` at `0x18006d446`
- `ntoskrnl!EtwWrite` at `0x18006d446`

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
0x18006d0ec  mov     [rsp-8+arg_0], rbx
0x18006d0f1  push    rbp
0x18006d0f2  push    rsi
0x18006d0f3  push    rdi
0x18006d0f4  push    r12
0x18006d0f6  push    r13
0x18006d0f8  push    r14
0x18006d0fa  push    r15
0x18006d0fc  lea     rbp, [rsp-130h]
0x18006d104  sub     rsp, 230h
0x18006d10b  mov     rax, cs:__security_cookie
0x18006d112  xor     rax, rsp
0x18006d115  mov     [rbp+160h+var_40], rax
0x18006d11c  xor     r12d, r12d
0x18006d11f  mov     r14, r8
0x18006d122  mov     rdi, rdx
0x18006d125  mov     [rbp+160h+var_1E0], r12
0x18006d129  mov     r15b, cl
0x18006d12c  mov     [rsp+260h+var_210], r12w
0x18006d132  xorps   xmm0, xmm0
0x18006d135  lea     rcx, [rbp+160h+var_80]; void *
0x18006d13c  lea     ebx, [r12+40h]
0x18006d141  xor     edx, edx; Val
0x18006d143  mov     r8d, ebx; Size
0x18006d146  mov     esi, r9d
0x18006d149  movups  [rsp+260h+var_1F8], xmm0
0x18006d14e  call    memset
0x18006d153  mov     r8d, ebx; Size
0x18006d156  mov     [rsp+260h+var_200], ebx
0x18006d15a  xor     edx, edx; Val
0x18006d15c  lea     rcx, [rbp+160h+var_100]; void *
0x18006d160  call    memset
0x18006d165  mov     r8d, ebx; Size
0x18006d168  mov     [rsp+260h+var_208], ebx
0x18006d16c  xor     edx, edx; Val
0x18006d16e  lea     rcx, [rbp+160h+var_C0]; void *
0x18006d175  call    memset
0x18006d17a  xor     eax, eax
0x18006d17c  mov     [rsp+260h+var_204], ebx
0x18006d180  mov     [rbp+160h+var_1C0], rax
0x18006d184  xorps   xmm0, xmm0
0x18006d187  mov     [rsp+260h+var_1E8], r12
0x18006d18c  mov     [rsp+260h+var_20C], r12w
0x18006d192  movups  [rbp+160h+var_1D8], xmm0
0x18006d196  test    r14, r14
0x18006d199  jnz     short loc_18006D1E9
0x18006d19b  test    esi, esi
0x18006d19d  jnz     short loc_18006D1A4
0x18006d19f  test    rdi, rdi
0x18006d1a2  jnz     short loc_18006D1ED
0x18006d1a4  mov     ebx, 0C000000Dh
0x18006d1a9  mov     rcx, [rsp+260h+var_1E8]
0x18006d1ae  call    CipReleaseProcessName
0x18006d1b3  mov     rcx, [rbp+160h+var_1E0]
0x18006d1b7  call    CipReleaseFileName
0x18006d1bc  mov     eax, ebx
0x18006d1be  mov     rcx, [rbp+160h+var_40]
0x18006d1c5  xor     rcx, rsp; StackCookie
0x18006d1c8  call    __security_check_cookie
0x18006d1cd  mov     rbx, [rsp+260h+arg_0]
0x18006d1d5  add     rsp, 230h
0x18006d1dc  pop     r15
0x18006d1de  pop     r14
0x18006d1e0  pop     r13
0x18006d1e2  pop     r12
0x18006d1e4  pop     rdi
0x18006d1e5  pop     rsi
0x18006d1e6  pop     rbp
0x18006d1e7  retn
0x18006d1e9  test    esi, esi
0x18006d1eb  jz      short loc_18006D1A4
0x18006d1ed  call    cs:__imp_PsGetCurrentProcess
0x18006d1f4  nop     dword ptr [rax+rax+00h]
0x18006d1f9  mov     rcx, rax
0x18006d1fc  lea     r8, [rsp+260h+var_1E8]
0x18006d201  lea     rdx, [rbp+160h+var_1D8]
0x18006d205  call    CipQueryProcessName
0x18006d20a  test    rdi, rdi
0x18006d20d  jz      short loc_18006D222
0x18006d20f  lea     r8, [rbp+160h+var_1E0]
0x18006d213  mov     rcx, rdi
0x18006d216  lea     rdx, [rsp+260h+var_1F8]
0x18006d21b  call    CipQueryFileName
0x18006d220  jmp     short loc_18006D270
0x18006d222  mov     [rsp+260h+var_228], r12
0x18006d227  lea     rax, [rbp+160h+var_1C8]
0x18006d22b  mov     [rsp+260h+var_230], r12
0x18006d230  lea     r9, [rsp+260h+var_1F8]
0x18006d235  mov     [rsp+260h+var_238], r12
0x18006d23a  mov     r8b, 1
0x18006d23d  mov     edx, esi
0x18006d23f  mov     [rsp+260h+UserData], rax
0x18006d244  mov     rcx, r14
0x18006d247  mov     [rbp+160h+var_1C8], r12
0x18006d24b  call    SIPolicyGetOriginalFilenameAndVersionFromImage
0x18006d250  test    eax, eax
0x18006d252  jns     short loc_18006D270
0x18006d254  mov     rax, [rbp+160h+var_1C0]
0x18006d258  mov     dword ptr [rsp+260h+var_1F8+4], eax
0x18006d25c  lea     rax, aInMemoryPeFile; "In_Memory_PE_File"
0x18006d263  mov     qword ptr [rsp+260h+var_1F8+8], rax
0x18006d268  mov     dword ptr [rsp+260h+var_1F8], 240022h
0x18006d270  lea     rax, [rsp+260h+var_200]
0x18006d275  mov     r13d, 800Ch
0x18006d27b  mov     [rsp+260h+var_220], rax
0x18006d280  mov     r9d, esi
0x18006d283  lea     rax, [rbp+160h+var_80]
0x18006d28a  mov     r8, r14
0x18006d28d  mov     [rsp+260h+var_228], rax
0x18006d292  mov     rdx, rdi
0x18006d295  mov     dword ptr [rsp+260h+var_230], r13d
0x18006d29a  xor     ecx, ecx
0x18006d29c  mov     byte ptr [rsp+260h+var_238], 1
0x18006d2a1  call    CipGetEnterpriseUmciFileHash
0x18006d2a6  mov     ebx, eax
0x18006d2a8  test    eax, eax
0x18006d2aa  js      loc_18006D1A9
0x18006d2b0  lea     rax, [rsp+260h+var_208]
0x18006d2b5  mov     r9d, esi
0x18006d2b8  mov     [rsp+260h+var_220], rax
0x18006d2bd  mov     r8, r14
0x18006d2c0  lea     rax, [rbp+160h+var_100]
0x18006d2c4  mov     rdx, rdi
0x18006d2c7  mov     [rsp+260h+var_228], rax
0x18006d2cc  xor     ecx, ecx
0x18006d2ce  mov     dword ptr [rsp+260h+var_230], 8004h
0x18006d2d6  mov     byte ptr [rsp+260h+var_238], r12b
0x18006d2db  call    CipGetEnterpriseUmciFileHash
0x18006d2e0  mov     ebx, eax
0x18006d2e2  test    eax, eax
0x18006d2e4  js      loc_18006D1A9
0x18006d2ea  lea     rax, [rsp+260h+var_204]
0x18006d2ef  mov     r9d, esi
0x18006d2f2  mov     [rsp+260h+var_220], rax
0x18006d2f7  mov     r8, r14
0x18006d2fa  lea     rax, [rbp+160h+var_C0]
0x18006d301  mov     rdx, rdi
0x18006d304  mov     [rsp+260h+var_228], rax
0x18006d309  xor     ecx, ecx
0x18006d30b  mov     dword ptr [rsp+260h+var_230], r13d
0x18006d310  mov     byte ptr [rsp+260h+var_238], r12b
0x18006d315  call    CipGetEnterpriseUmciFileHash
0x18006d31a  mov     ebx, eax
0x18006d31c  test    eax, eax
0x18006d31e  js      loc_18006D1A9
0x18006d324  call    cs:__imp_IoGetActivityIdThread
0x18006d32b  nop     dword ptr [rax+rax+00h]
0x18006d330  movzx   ecx, word ptr [rsp+260h+var_1F8]
0x18006d335  lea     rdx, CiDynamicCodeTrustAudited
0x18006d33c  mov     r8, rax; ActivityId
0x18006d33f  shr     cx, 1
0x18006d342  mov     [rsp+260h+var_210], cx
0x18006d347  lea     rax, [rsp+260h+var_210]
0x18006d34c  movzx   ecx, word ptr [rbp+160h+var_1D8]
0x18006d350  mov     r9d, 0Bh; UserDataCount
0x18006d356  mov     [rbp+160h+var_1B0.Ptr], rax
0x18006d35a  movzx   eax, word ptr [rsp+260h+var_1F8]
0x18006d35f  mov     [rbp+160h+var_198], eax
0x18006d362  lea     rax, [rsp+260h+var_20C]
0x18006d367  mov     [rbp+160h+var_190], rax
0x18006d36b  mov     rax, qword ptr [rbp+160h+var_1D8+8]
0x18006d36f  mov     [rbp+160h+var_180], rax
0x18006d373  movzx   eax, word ptr [rbp+160h+var_1D8]
0x18006d377  mov     [rbp+160h+var_178], eax
0x18006d37a  lea     rax, [rbp+160h+arg_20]
0x18006d381  mov     [rbp+160h+var_170], rax
0x18006d385  lea     rax, [rsp+260h+var_208]
0x18006d38a  mov     [rbp+160h+var_160], rax
0x18006d38e  lea     rax, [rbp+160h+var_100]
0x18006d392  mov     [rbp+160h+var_150], rax
0x18006d396  mov     eax, [rsp+260h+var_208]
0x18006d39a  mov     [rbp+160h+var_148], eax
0x18006d39d  lea     rax, [rsp+260h+var_204]
0x18006d3a2  mov     [rbp+160h+var_140], rax
0x18006d3a6  lea     rax, [rbp+160h+var_C0]
0x18006d3ad  mov     [rbp+160h+var_130], rax
0x18006d3b1  mov     eax, [rsp+260h+var_204]
0x18006d3b5  mov     [rbp+160h+var_128], eax
0x18006d3b8  lea     rax, [rsp+260h+var_200]
0x18006d3bd  mov     [rbp+160h+var_120], rax
0x18006d3c1  lea     rax, [rbp+160h+var_80]
0x18006d3c8  shr     cx, 1
0x18006d3cb  mov     [rbp+160h+var_110], rax
0x18006d3cf  test    r15b, r15b
0x18006d3d2  mov     eax, [rsp+260h+var_200]
0x18006d3d6  mov     [rbp+160h+var_108], eax
0x18006d3d9  lea     rax, CiDynamicCodeTrustFailed
0x18006d3e0  mov     [rsp+260h+var_20C], cx
0x18006d3e5  cmovz   rdx, rax; EventDescriptor
0x18006d3e9  mov     rcx, qword ptr [rsp+260h+var_1F8+8]
0x18006d3ee  lea     rax, [rbp+160h+var_1B0]
0x18006d3f2  mov     [rbp+160h+var_1A0], rcx
0x18006d3f6  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d3fd  mov     [rsp+260h+UserData], rax; UserData
0x18006d402  mov     qword ptr [rbp+160h+var_1B0.Size], 2
0x18006d40a  mov     [rbp+160h+var_194], r12d
0x18006d40e  mov     [rbp+160h+var_188], 2
0x18006d416  mov     [rbp+160h+var_174], r12d
0x18006d41a  mov     [rbp+160h+var_168], 4
0x18006d422  mov     [rbp+160h+var_158], 4
0x18006d42a  mov     [rbp+160h+var_144], r12d
0x18006d42e  mov     [rbp+160h+var_138], 4
0x18006d436  mov     [rbp+160h+var_124], r12d
0x18006d43a  mov     [rbp+160h+var_118], 4
0x18006d442  mov     [rbp+160h+var_104], r12d
0x18006d446  call    cs:__imp_EtwWrite
0x18006d44d  nop     dword ptr [rax+rax+00h]
0x18006d452  mov     ebx, eax
0x18006d454  jmp     loc_18006D1A9
```
