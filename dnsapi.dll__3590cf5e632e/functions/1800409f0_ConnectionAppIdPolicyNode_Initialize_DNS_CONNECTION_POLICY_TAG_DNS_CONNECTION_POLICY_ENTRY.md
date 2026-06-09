# ConnectionAppIdPolicyNode::Initialize(DNS_CONNECTION_POLICY_TAG,_DNS_CONNECTION_POLICY_ENTRY *)

- ea: `0x1800409f0`
- end: `0x180040e61`
- name: `?Initialize@ConnectionAppIdPolicyNode@@QEAAJW4DNS_CONNECTION_POLICY_TAG@@PEAU_DNS_CONNECTION_POLICY_ENTRY@@@Z`
- size: `1137`
- prototype: `__int64 __fastcall(ConnectionAppIdPolicyNode *__hidden this, enum DNS_CONNECTION_POLICY_TAG, struct _DNS_CONNECTION_POLICY_ENTRY *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fe10`
- `0x180040824`

## callees

- `0x1800409f0`
- `0x1800cafec`
- `0x1800dc9e0`
- `0x1800dcc34`
- `0x1800df1ec`
- `0x1800e1720`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180040bdd`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180040bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040d7f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180040d14`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180040d14`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180040cfd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180040cfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040b8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040b8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040b1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040b1b`

## pseudocode

```c
__int64 __fastcall ConnectionAppIdPolicyNode::Initialize(
        ConnectionAppIdPolicyNode *this,
        enum DNS_CONNECTION_POLICY_TAG a2,
        struct _DNS_CONNECTION_POLICY_ENTRY *a3)
{
  int v6; // eax
  PCWSTR v7; // rbp
  _WORD *v8; // rcx
  unsigned __int64 pwszAppId; // rcx
  __int64 v10; // rbx
  unsigned int v11; // r15d
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // r15d
  __int64 v17; // rcx
  _WORD *v18; // rax
  _WORD *v19; // rdi
  WCHAR *v20; // rsi
  void *v21; // rsi
  int v22; // eax
  unsigned __int16 *v23; // r9
  __int64 v24; // rdx
  int v25; // r8d
  PBYTE pbAppSid; // r8
  DWORD LengthSid; // eax
  signed int LastError; // eax

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qdq(1035, 24, (unsigned int)WPP_71080afd593b3f642843e61775452ce0_Traceguids, (_DWORD)this, a2, (__int64)a3);
  if ( !a3 )
  {
    v11 = -2147024809;
    goto LABEL_38;
  }
  v6 = *((_DWORD *)this + 4);
  v7 = L"*";
  if ( v6 )
  {
    v8 = (_WORD *)*((_QWORD *)this + 1);
    *((_DWORD *)this + 4) = 0;
    *v8 = 0;
    v6 = *((_DWORD *)this + 4);
  }
  pwszAppId = (unsigned __int64)a3->pwszAppId;
  if ( pwszAppId && *(_WORD *)pwszAppId && *(_WORD *)pwszAppId != 42 )
    v7 = a3->pwszAppId;
  if ( v6 )
  {
    pwszAppId = *((_QWORD *)this + 1);
    *((_DWORD *)this + 4) = 0;
    *(_WORD *)pwszAppId = 0;
  }
  if ( !v7 )
    goto LABEL_41;
  v10 = -1;
  do
    ++v10;
  while ( v7[v10] );
  v11 = 0;
  if ( (_DWORD)v10 )
  {
    v12 = v10 + *((_DWORD *)this + 4) + 1;
    if ( *((_DWORD *)this + 5) >= v12 )
    {
LABEL_27:
      v21 = (void *)(*((_QWORD *)this + 1) + 2LL * *((unsigned int *)this + 4));
      memcpy_0(v21, v7, 2LL * (unsigned int)v10);
      *((_WORD *)v21 + (unsigned int)v10) = 0;
      *((_DWORD *)this + 4) += v10;
      goto LABEL_28;
    }
    v13 = v12 + 2;
    v14 = 256;
    if ( v13 > 0x100 )
    {
      if ( v13 > 0x400 )
      {
        v14 = 4096;
        if ( v13 <= 0x1000 )
          v14 = 1024;
      }
    }
    else
    {
      v14 = 64;
    }
    v15 = -v14 & (v14 + v13 - 1);
    v16 = v15 - 1;
    if ( (unsigned int)(v15 - 1) <= 0xFFFFFFE )
    {
      v17 = (unsigned int)(2 * v15);
      if ( g_fWxHeapExtensionInitialized )
        v18 = (_WORD *)((__int64 (__fastcall *)(__int64))qword_180111EB8)(v17);
      else
        v18 = HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v17);
      v19 = v18;
      if ( !v18 )
      {
        v11 = -2147024882;
        goto LABEL_38;
      }
      *v18 = 0;
      v20 = (WCHAR *)*((_QWORD *)this + 1);
      memcpy_0(v18, v20, 2LL * *((unsigned int *)this + 4));
      v19[*((unsigned int *)this + 4)] = 0;
      *((_DWORD *)this + 5) = v16;
      *((_QWORD *)this + 1) = v19;
      v11 = 0;
      if ( v20 && v20 != &word_1800F66E0 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v20);
        else
          HeapFree(g_hWxProcessHeap, 0, v20);
      }
      goto LABEL_27;
    }
LABEL_41:
    v11 = -2147024809;
    goto LABEL_38;
  }
LABEL_28:
  v22 = *((_DWORD *)this + 4);
  if ( v22 )
    _wcslwr_s(*((wchar_t **)this + 1), (unsigned int)(v22 + 1));
  v23 = (unsigned __int16 *)*((_QWORD *)this + 1);
  v24 = 0;
  v25 = 0;
  if ( v23 )
  {
    do
    {
      pwszAppId = *v23;
      v24 = (unsigned int)dword_1800F62C0[pwszAppId >> 8]
          ^ __ROL4__(dword_1800F62C0[(unsigned __int8)pwszAppId] ^ __ROL4__(v24, 1), 1);
      if ( !(_WORD)pwszAppId )
        break;
      ++v23;
      ++v25;
    }
    while ( v25 != -1 );
  }
  *((_DWORD *)this + 6) = v24;
  pbAppSid = a3->pbAppSid;
  if ( !pbAppSid || !a3->cbAppSid )
  {
LABEL_35:
    if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_q_sid_SS(
        pwszAppId,
        v24,
        (__int64)pbAppSid,
        (__int64)this,
        (char *)a3->pbAppSid,
        a3->pwszAppId,
        a3->pwszHost);
    *((_DWORD *)this + 1) = a2;
    goto LABEL_38;
  }
  if ( CopySid(0x44u, *((PSID *)this + 12), pbAppSid) )
  {
    v11 = 0;
    LengthSid = GetLengthSid(*((PSID *)this + 12));
    *((_DWORD *)this + 26) = LengthSid;
    pbAppSid = (PBYTE)a3->cbAppSid;
    if ( LengthSid != (_DWORD)pbAppSid )
    {
      if ( (byte_1801119D3 & 0x40) != 0 )
        WPP_SF_qDD(542, 25, WPP_71080afd593b3f642843e61775452ce0_Traceguids, this, LengthSid, (_DWORD)pbAppSid);
      if ( *((_DWORD *)this + 26) != a3->cbAppSid )
      {
        v11 = -2147024809;
        goto LABEL_38;
      }
    }
    goto LABEL_35;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( (v11 & 0x80000000) == 0 )
    v11 = -2147418113;
LABEL_38:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 27, WPP_71080afd593b3f642843e61775452ce0_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800409f0  sub     rsp, 88h
0x1800409f7  mov     [rsp+88h+var_20], r12
0x1800409fc  mov     r12, r8
0x1800409ff  mov     [rsp+88h+var_28], r13
0x180040a04  mov     r13d, edx
0x180040a07  mov     [rsp+88h+var_30], r14
0x180040a0c  mov     r14, rcx
0x180040a0f  mov     [rsp+88h+var_44], 0
0x180040a17  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180040a1e  jnz     loc_180040DC9
0x180040a24  mov     [rsp+88h+var_38], r15
0x180040a29  test    r12, r12
0x180040a2c  jz      loc_180040DB6
0x180040a32  mov     eax, [r14+10h]
0x180040a36  mov     [rsp+88h+var_8], rbp
0x180040a3e  lea     rbp, asc_1800F5998; "*"
0x180040a45  test    eax, eax
0x180040a47  jz      short loc_180040A5E
0x180040a49  mov     rcx, [r14+8]
0x180040a4d  xor     eax, eax
0x180040a4f  mov     dword ptr [r14+10h], 0
0x180040a57  mov     [rcx], ax
0x180040a5a  mov     eax, [r14+10h]
0x180040a5e  mov     rcx, [r12+8]
0x180040a63  test    rcx, rcx
0x180040a66  jz      short loc_180040A78
0x180040a68  movzx   edx, word ptr [rcx]
0x180040a6b  test    dx, dx
0x180040a6e  jz      short loc_180040A78
0x180040a70  cmp     dx, 2Ah ; '*'
0x180040a74  cmovnz  rbp, rcx
0x180040a78  test    eax, eax
0x180040a7a  jnz     loc_180040C97
0x180040a80  mov     [rsp+88h+arg_8], rbx
0x180040a88  mov     [rsp+88h+var_10], rsi
0x180040a8d  mov     [rsp+88h+var_18], rdi
0x180040a92  test    rbp, rbp
0x180040a95  jz      loc_180040CAD
0x180040a9b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180040aa2  inc     rbx
0x180040aa5  cmp     word ptr [rbp+rbx*2+0], 0
0x180040aab  jnz     short loc_180040AA2
0x180040aad  xor     r15d, r15d
0x180040ab0  test    ebx, ebx
0x180040ab2  jz      loc_180040E2F
0x180040ab8  mov     ecx, [r14+10h]
0x180040abc  inc     ecx
0x180040abe  add     ecx, ebx
0x180040ac0  cmp     [r14+14h], ecx
0x180040ac4  jnb     loc_180040B9B
0x180040aca  add     ecx, 2
0x180040acd  mov     eax, 100h
0x180040ad2  cmp     ecx, eax
0x180040ad4  ja      loc_180040CBD
0x180040ada  mov     eax, 40h ; '@'
0x180040adf  dec     ecx
0x180040ae1  add     ecx, eax
0x180040ae3  neg     eax
0x180040ae5  and     ecx, eax
0x180040ae7  lea     r15d, [rcx-1]
0x180040aeb  cmp     r15d, 0FFFFFFEh
0x180040af2  ja      loc_180040CAD
0x180040af8  add     ecx, ecx
0x180040afa  mov     [rsp+88h+var_44], 0
0x180040b02  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180040b09  jnz     loc_180040E3D
0x180040b0f  mov     r8d, ecx; dwBytes
0x180040b12  xor     edx, edx; dwFlags
0x180040b14  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180040b1b  call    cs:__imp_HeapAlloc
0x180040b22  nop     dword ptr [rax+rax+00h]
0x180040b27  mov     rdi, rax
0x180040b2a  test    rax, rax
0x180040b2d  jz      loc_180040E4E
0x180040b33  xor     eax, eax
0x180040b35  mov     rcx, rdi; void *
0x180040b38  mov     [rdi], ax
0x180040b3b  mov     rsi, [r14+8]
0x180040b3f  mov     r8d, [r14+10h]
0x180040b43  mov     rdx, rsi; Src
0x180040b46  add     r8, r8; Size
0x180040b49  call    memcpy_0
0x180040b4e  mov     ecx, [r14+10h]
0x180040b52  xor     eax, eax
0x180040b54  mov     [rdi+rcx*2], ax
0x180040b58  mov     [r14+14h], r15d
0x180040b5c  mov     [r14+8], rdi
0x180040b60  xor     r15d, r15d
0x180040b63  test    rsi, rsi
0x180040b66  jz      short loc_180040B9B
0x180040b68  lea     rax, word_1800F66E0
0x180040b6f  cmp     rsi, rax
0x180040b72  jz      short loc_180040B9B
0x180040b74  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r15d; int g_fWxHeapExtensionInitialized
0x180040b7b  jnz     loc_180040DF1
0x180040b81  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180040b88  mov     r8, rsi; lpMem
0x180040b8b  xor     edx, edx; dwFlags
0x180040b8d  call    cs:__imp_HeapFree
0x180040b94  nop     dword ptr [rax+rax+00h]
0x180040b99  jmp     short loc_180040BA4
0x180040b9b  test    r15d, r15d
0x180040b9e  js      loc_180040CB3
0x180040ba4  mov     ecx, [r14+10h]
0x180040ba8  mov     rdx, rbp; Src
0x180040bab  mov     rax, [r14+8]
0x180040baf  lea     rsi, [rax+rcx*2]
0x180040bb3  mov     eax, ebx
0x180040bb5  mov     rcx, rsi; void *
0x180040bb8  lea     rdi, [rax+rax]
0x180040bbc  mov     r8, rdi; Size
0x180040bbf  call    memcpy_0
0x180040bc4  xor     eax, eax
0x180040bc6  mov     [rdi+rsi], ax
0x180040bca  add     [r14+10h], ebx
0x180040bce  mov     eax, [r14+10h]
0x180040bd2  test    eax, eax
0x180040bd4  jz      short loc_180040BE9
0x180040bd6  mov     rcx, [r14+8]; String
0x180040bda  lea     edx, [rax+1]; SizeInWords
0x180040bdd  call    cs:__imp__wcslwr_s
0x180040be4  nop     dword ptr [rax+rax+00h]
0x180040be9  mov     r9, [r14+8]
0x180040bed  xor     edx, edx
0x180040bef  xor     r8d, r8d
0x180040bf2  test    r9, r9
0x180040bf5  jz      short loc_180040C29
0x180040bf7  lea     r10, dword_1800F62C0
0x180040bfe  movzx   ecx, word ptr [r9]; int
0x180040c02  rol     edx, 1
0x180040c04  movzx   eax, cl
0x180040c07  xor     edx, [r10+rax*4]
0x180040c0b  mov     eax, ecx
0x180040c0d  shr     rax, 8
0x180040c11  rol     edx, 1
0x180040c13  xor     edx, [r10+rax*4]; int
0x180040c17  test    cx, cx
0x180040c1a  jz      short loc_180040C29
0x180040c1c  add     r9, 2
0x180040c20  inc     r8d
0x180040c23  cmp     r8d, 0FFFFFFFFh
0x180040c27  jb      short loc_180040BFE
0x180040c29  mov     [r14+18h], edx
0x180040c2d  mov     r8, [r12+18h]; int
0x180040c32  test    r8, r8
0x180040c35  jz      short loc_180040C43
0x180040c37  cmp     dword ptr [r12+10h], 0
0x180040c3d  jnz     loc_180040CF4
0x180040c43  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x180040c4a  jnz     loc_180040E05
0x180040c50  mov     [r14+4], r13d
0x180040c54  mov     rsi, [rsp+88h+var_10]
0x180040c59  mov     rbx, [rsp+88h+arg_8]
0x180040c61  mov     rdi, [rsp+88h+var_18]
0x180040c66  mov     rbp, [rsp+88h+var_8]
0x180040c6e  mov     r14, [rsp+88h+var_30]
0x180040c73  mov     r13, [rsp+88h+var_28]
0x180040c78  mov     r12, [rsp+88h+var_20]
0x180040c7d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180040c84  jnz     short loc_180040CD9
0x180040c86  mov     eax, r15d
0x180040c89  mov     r15, [rsp+88h+var_38]
0x180040c8e  add     rsp, 88h
0x180040c95  retn
0x180040c97  mov     rcx, [r14+8]
0x180040c9b  xor     eax, eax
0x180040c9d  mov     dword ptr [r14+10h], 0
0x180040ca5  mov     [rcx], ax
0x180040ca8  jmp     loc_180040A80
0x180040cad  mov     r15d, 80070057h
0x180040cb3  mov     [rsp+88h+var_44], 1E8h
0x180040cbb  jmp     short loc_180040C54
0x180040cbd  mov     edx, 400h
0x180040cc2  cmp     ecx, edx
0x180040cc4  jbe     loc_180040ADF
0x180040cca  mov     eax, 1000h
0x180040ccf  cmp     ecx, eax
0x180040cd1  cmovbe  eax, edx
0x180040cd4  jmp     loc_180040ADF
0x180040cd9  mov     edx, 1Bh
0x180040cde  lea     r8, WPP_71080afd593b3f642843e61775452ce0_Traceguids
0x180040ce5  mov     ecx, 40Bh
0x180040cea  mov     r9d, r15d
0x180040ced  call    WPP_SF_d
0x180040cf2  jmp     short loc_180040C86
0x180040cf4  mov     rdx, [r14+60h]; pDestinationSid
0x180040cf8  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180040cfd  call    cs:__imp_CopySid
0x180040d04  nop     dword ptr [rax+rax+00h]
0x180040d09  test    eax, eax
0x180040d0b  jz      short loc_180040D7F
0x180040d0d  mov     rcx, [r14+60h]; pSid
0x180040d11  xor     r15d, r15d
0x180040d14  call    cs:__imp_GetLengthSid
0x180040d1b  nop     dword ptr [rax+rax+00h]
0x180040d20  mov     [r14+68h], eax
0x180040d24  mov     r8d, [r12+10h]
0x180040d29  cmp     eax, r8d
0x180040d2c  jz      loc_180040C43
0x180040d32  test    cs:byte_1801119D3, 40h
0x180040d39  jz      short loc_180040D5D
0x180040d3b  mov     dword ptr [rsp+88h+var_60], r8d
0x180040d40  mov     edx, 19h
0x180040d45  lea     r8, WPP_71080afd593b3f642843e61775452ce0_Traceguids
0x180040d4c  mov     dword ptr [rsp+88h+pSid], eax
0x180040d50  mov     ecx, 21Eh
0x180040d55  mov     r9, r14
0x180040d58  call    WPP_SF_qDD
0x180040d5d  mov     eax, [r12+10h]
0x180040d62  cmp     [r14+68h], eax
0x180040d66  jz      loc_180040C43
0x180040d6c  mov     r15d, 80070057h
0x180040d72  mov     [rsp+88h+var_44], 208h
0x180040d7a  jmp     loc_180040C54
0x180040d7f  call    cs:__imp_GetLastError
0x180040d86  nop     dword ptr [rax+rax+00h]
0x180040d8b  mov     r15d, eax
0x180040d8e  test    eax, eax
0x180040d90  jle     short loc_180040D9D
0x180040d92  movzx   r15d, ax
0x180040d96  or      r15d, 80070000h
0x180040d9d  test    r15d, r15d
0x180040da0  mov     [rsp+88h+var_44], 1FBh
0x180040da8  mov     eax, 8000FFFFh
0x180040dad  cmovns  r15d, eax
0x180040db1  jmp     loc_180040C54
0x180040db6  mov     r15d, 80070057h
0x180040dbc  mov     [rsp+88h+var_44], 1DEh
0x180040dc4  jmp     loc_180040C6E
0x180040dc9  mov     edx, 18h
0x180040dce  mov     [rsp+88h+var_60], r12
0x180040dd3  mov     ecx, 40Bh
0x180040dd8  mov     dword ptr [rsp+88h+pSid], r13d
0x180040ddd  mov     r9, r14
0x180040de0  lea     r8, WPP_71080afd593b3f642843e61775452ce0_Traceguids
0x180040de7  call    WPP_SF_qdq
0x180040dec  jmp     loc_180040A24
0x180040df1  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180040df8  mov     rcx, rsi
0x180040dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e00  jmp     loc_180040BA4
0x180040e05  mov     rax, [r12]
0x180040e09  mov     r9, r14; int
0x180040e0c  mov     [rsp+88h+var_58], rax; __int64
0x180040e11  mov     rax, [r12+8]
0x180040e16  mov     [rsp+88h+var_60], rax; __int64
0x180040e1b  mov     rax, [r12+18h]
0x180040e20  mov     [rsp+88h+pSid], rax; pSid
0x180040e25  call    WPP_SF_q_sid_SS
0x180040e2a  jmp     loc_180040C50
0x180040e2f  test    r15d, r15d
0x180040e32  jns     loc_180040BCE
0x180040e38  jmp     loc_180040CB3
0x180040e3d  mov     rax, cs:qword_180111EB8
0x180040e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e49  jmp     loc_180040B27
0x180040e4e  mov     [rsp+88h+var_44], 34h ; '4'
0x180040e56  mov     r15d, 8007000Eh
0x180040e5c  jmp     loc_180040CB3
```
