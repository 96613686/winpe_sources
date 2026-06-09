# Pku2uLogProvider::LogQueryMetadata(_LARGE_INTEGER,_LARGE_INTEGER,_PKU2U_SECONDARY_CREDENTIAL *,_SecPkgContext_IssuerListInfoEx *,_PKU2U_CONTEXT *,long)

- ea: `0x18000a370`
- end: `0x18000a6b3`
- name: `?LogQueryMetadata@Pku2uLogProvider@@SAXT_LARGE_INTEGER@@0PEAU_PKU2U_SECONDARY_CREDENTIAL@@PEAU_SecPkgContext_IssuerListInfoEx@@PEAU_PKU2U_CONTEXT@@J@Z`
- size: `835`
- prototype: `void __fastcall(union _LARGE_INTEGER, union _LARGE_INTEGER, struct _PKU2U_SECONDARY_CREDENTIAL *, struct _SecPkgContext_IssuerListInfoEx *, struct _PKU2U_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009070`

## callees

- `0x18000a370`
- `0x180014d60`
- `0x1800153d0`
- `0x180017af0`
- `0x1800210f0`
- `0x180021a54`
- `0x180044d98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18000a4ab`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18000a4ab`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a4bd`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a4bd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a680`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a680`

## pseudocode

```c
void __fastcall Pku2uLogProvider::LogQueryMetadata(
        union _LARGE_INTEGER a1,
        union _LARGE_INTEGER a2,
        struct _PKU2U_SECONDARY_CREDENTIAL *a3,
        struct _SecPkgContext_IssuerListInfoEx *a4,
        struct _PKU2U_CONTEXT *a5,
        int a6)
{
  TraceLoggingCorrelationVector *v10; // rcx
  LARGE_INTEGER v11; // rcx
  LONGLONG v12; // rax
  char v13; // r12
  int v14; // ebx
  __int64 v15; // r13
  BYTE *pbData; // r14
  DWORD cbData; // edi
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // edx
  GUID *v21; // r8
  char v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  _DWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  struct _PKU2U_CONTEXT *v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR Str; // [rsp+70h] [rbp-90h] BYREF
  __int16 *v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+8Ch] [rbp-74h]
  __int64 *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  _DWORD *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  GUID *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  char *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  int *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  struct _PKU2U_CONTEXT **v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  char *v47; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+108h] [rbp+8h]
  int v49; // [rsp+10Ch] [rbp+Ch]
  char v50[16]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v51; // [rsp+190h] [rbp+90h]
  __int128 v52; // [rsp+1A0h] [rbp+A0h]
  __int128 v53; // [rsp+1B0h] [rbp+B0h]
  __int128 v54; // [rsp+1C0h] [rbp+C0h]
  __int128 v55; // [rsp+1D0h] [rbp+D0h]
  __int128 v56; // [rsp+1E0h] [rbp+E0h]
  __int128 v57; // [rsp+1F0h] [rbp+F0h]
  char v58; // [rsp+200h] [rbp+100h]

  if ( Pku2uLogProvider::m_initialized && Pku2uLogProvider::IsEnabled(a1.LowPart, a2.QuadPart) )
  {
    v58 = 0;
    *(_OWORD *)v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    if ( !TraceLoggingCorrelationVector::Increment(v10, v50) )
      v50[0] = 0;
    v11 = Pku2uLogProvider::m_perfCtrFreq;
    if ( !Pku2uLogProvider::m_perfCtrFreq.QuadPart )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v11.QuadPart = 1;
      Pku2uLogProvider::m_perfCtrFreq.QuadPart = 1;
    }
    v12 = 1000000 * (a2.QuadPart - a1.QuadPart);
    v13 = 0;
    v14 = 0;
    v15 = v12 / v11.QuadPart;
    if ( a4 && a4->cIssuers )
    {
      while ( 1 )
      {
        pbData = a4->aIssuers[v14].pbData;
        if ( pbData )
        {
          cbData = a4->aIssuers[v14].cbData;
          if ( cbData )
          {
            memset_0(&Str, 0, 0x104u);
            _o_strncpy_s(&Str, 259, pbData, cbData);
            if ( strstr((const char *)&Str, "Container Authentication Intermediate CA") )
              break;
          }
        }
        if ( ++v14 >= a4->cIssuers )
          goto LABEL_15;
      }
      v13 = 1;
    }
LABEL_15:
    v18 = *((_QWORD *)Pku2uLogProvider::Instance() + 1);
    if ( *(_DWORD *)v18 > 5u
      && (*(_QWORD *)(v18 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v18 + 24) & 0x400000000000LL) == *(_QWORD *)(v18 + 24) )
    {
      v25 = a5;
      v23 = a6;
      v19 = -1;
      v22 = v13;
      if ( a3 )
      {
        v20 = *((_DWORD *)a3 + 8);
        v21 = (GUID *)((char *)a3 + 120);
      }
      else
      {
        v21 = &GUID_NULL;
        v20 = -1;
      }
      v24[0] = v20;
      v26 = v15;
      v27 = 0x1000000;
      do
        ++v19;
      while ( v50[v19] );
      v39 = v21;
      v48 = v19 + 1;
      v47 = v50;
      v45 = &v25;
      EventDescriptor.Keyword = 0x400000000000LL;
      v43 = &v23;
      v49 = 0;
      v41 = &v22;
      v46 = 8;
      v37 = v24;
      v35 = &v26;
      v33 = &v27;
      *(_DWORD *)&EventDescriptor.Level = 5;
      Str.Ptr = *(_QWORD *)(v18 + 8);
      v44 = 4;
      v42 = 1;
      v40 = 16;
      v38 = 4;
      v36 = 8;
      v34 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      Str.Size = *(unsigned __int16 *)Str.Ptr;
      v30 = &word_18004CABE;
      Str.Reserved = 2;
      v31 = 127;
      v32 = 1;
      v24[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v18 + 32), &EventDescriptor, 0, 0, 0xAu, &Str);
    }
  }
}

```

## disassembly

```asm
0x18000a370  push    rbp
0x18000a372  push    rbx
0x18000a373  push    rsi
0x18000a374  push    rdi
0x18000a375  push    r15
0x18000a377  lea     rbp, [rsp-130h]
0x18000a37f  sub     rsp, 230h
0x18000a386  mov     rax, cs:__security_cookie
0x18000a38d  xor     rax, rsp
0x18000a390  mov     [rbp+150h+var_40], rax
0x18000a397  cmp     cs:?m_initialized@Pku2uLogProvider@@0_NA, 0; bool Pku2uLogProvider::m_initialized
0x18000a39e  mov     rsi, r9
0x18000a3a1  mov     r15, r8
0x18000a3a4  mov     rbx, rdx
0x18000a3a7  mov     rdi, rcx
0x18000a3aa  jz      loc_18000A696
0x18000a3b0  call    ?IsEnabled@Pku2uLogProvider@@SA_NE_K@Z; Pku2uLogProvider::IsEnabled(uchar,unsigned __int64)
0x18000a3b5  test    al, al
0x18000a3b7  jz      loc_18000A696
0x18000a3bd  xorps   xmm0, xmm0
0x18000a3c0  mov     [rsp+250h+arg_10], r12
0x18000a3c8  xor     eax, eax
0x18000a3ca  mov     [rsp+250h+var_28], r13
0x18000a3d2  lea     rdx, [rbp+150h+var_D0]; char *
0x18000a3d9  mov     [rbp+150h+var_50], al
0x18000a3df  movups  xmmword ptr [rbp+150h+var_D0], xmm0
0x18000a3e6  movups  [rbp+150h+var_C0], xmm0
0x18000a3ed  movups  [rbp+150h+var_B0], xmm0
0x18000a3f4  movups  [rbp+150h+var_A0], xmm0
0x18000a3fb  movups  [rbp+150h+var_90], xmm0
0x18000a402  movups  [rbp+150h+var_80], xmm0
0x18000a409  movups  [rbp+150h+var_70], xmm0
0x18000a410  movups  [rbp+150h+var_60], xmm0
0x18000a417  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18000a41c  test    al, al
0x18000a41e  jnz     short loc_18000A426
0x18000a420  mov     [rbp+150h+var_D0], al
0x18000a426  mov     rcx, qword ptr cs:?m_perfCtrFreq@Pku2uLogProvider@@0T_LARGE_INTEGER@@A; _LARGE_INTEGER Pku2uLogProvider::m_perfCtrFreq ...
0x18000a42d  test    rcx, rcx
0x18000a430  jnz     short loc_18000A443
0x18000a432  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a437  mov     ecx, 1
0x18000a43c  mov     qword ptr cs:?m_perfCtrFreq@Pku2uLogProvider@@0T_LARGE_INTEGER@@A, rcx; _LARGE_INTEGER Pku2uLogProvider::m_perfCtrFreq ...
0x18000a443  sub     rbx, rdi
0x18000a446  mov     [rsp+250h+var_30], r14
0x18000a44e  imul    rax, rbx, 0F4240h
0x18000a455  xor     r12b, r12b
0x18000a458  xor     ebx, ebx
0x18000a45a  cqo
0x18000a45c  idiv    rcx
0x18000a45f  mov     r13, rax
0x18000a462  test    rsi, rsi
0x18000a465  jz      short loc_18000A4D6
0x18000a467  cmp     [rsi+8], ebx
0x18000a46a  jbe     short loc_18000A4D6
0x18000a46c  nop     dword ptr [rax+00h]
0x18000a470  mov     rax, [rsi]
0x18000a473  mov     ecx, ebx
0x18000a475  add     rcx, rcx
0x18000a478  mov     r14, [rax+rcx*8+8]
0x18000a47d  test    r14, r14
0x18000a480  jz      short loc_18000A4C8
0x18000a482  mov     edi, [rax+rcx*8]
0x18000a485  test    edi, edi
0x18000a487  jz      short loc_18000A4C8
0x18000a489  xor     edx, edx; Val
0x18000a48b  lea     rcx, [rsp+250h+Str]; void *
0x18000a490  mov     r8d, 104h; Size
0x18000a496  call    memset_0
0x18000a49b  mov     r9d, edi
0x18000a49e  lea     rcx, [rsp+250h+Str]
0x18000a4a3  mov     r8, r14
0x18000a4a6  mov     edx, 103h
0x18000a4ab  call    cs:__imp__o_strncpy_s
0x18000a4b1  lea     rdx, SubStr; "Container Authentication Intermediate C"...
0x18000a4b8  lea     rcx, [rsp+250h+Str]; Str
0x18000a4bd  call    cs:__imp_strstr
0x18000a4c3  test    rax, rax
0x18000a4c6  jnz     short loc_18000A4D1
0x18000a4c8  inc     ebx
0x18000a4ca  cmp     ebx, [rsi+8]
0x18000a4cd  jb      short loc_18000A470
0x18000a4cf  jmp     short loc_18000A4D4
0x18000a4d1  mov     r12b, 1
0x18000a4d4  xor     ebx, ebx
0x18000a4d6  call    ?Instance@Pku2uLogProvider@@KAPEAV1@XZ; Pku2uLogProvider::Instance(void)
0x18000a4db  mov     r14, [rsp+250h+var_30]
0x18000a4e3  mov     rcx, [rax+8]
0x18000a4e7  mov     eax, [rcx]
0x18000a4e9  cmp     eax, 5
0x18000a4ec  jbe     loc_18000A686
0x18000a4f2  mov     rdx, [rcx+18h]
0x18000a4f6  mov     r9, 400000000000h
0x18000a500  mov     rax, [rcx+10h]
0x18000a504  test    r9, rax
0x18000a507  jz      loc_18000A686
0x18000a50d  mov     rax, rdx
0x18000a510  and     rax, r9
0x18000a513  cmp     rax, rdx
0x18000a516  jnz     loc_18000A686
0x18000a51c  mov     rax, [rbp+150h+arg_20]
0x18000a523  mov     [rsp+250h+var_210], rax
0x18000a528  mov     eax, [rbp+150h+arg_28]
0x18000a52e  mov     [rsp+250h+var_21C], eax
0x18000a532  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a539  mov     [rsp+250h+var_220], r12b
0x18000a53e  test    r15, r15
0x18000a541  jz      short loc_18000A54D
0x18000a543  mov     edx, [r15+20h]
0x18000a547  lea     r8, [r15+78h]
0x18000a54b  jmp     short loc_18000A556
0x18000a54d  lea     r8, GUID_NULL
0x18000a554  mov     edx, eax
0x18000a556  mov     [rsp+250h+var_218], edx
0x18000a55a  lea     rdx, [rbp+150h+var_D0]
0x18000a561  mov     [rsp+250h+var_208], r13
0x18000a566  mov     [rsp+250h+var_200], 1000000h
0x18000a56f  nop
0x18000a570  inc     rax
0x18000a573  cmp     byte ptr [rdx+rax], 0
0x18000a577  jnz     short loc_18000A570
0x18000a579  inc     eax
0x18000a57b  mov     [rbp+150h+var_190], r8
0x18000a57f  mov     [rbp+150h+var_148], eax
0x18000a582  lea     rdx, [rbp+150h+var_D0]
0x18000a589  mov     [rbp+150h+var_150], rdx
0x18000a58d  lea     rax, [rsp+250h+var_210]
0x18000a592  mov     [rbp+150h+var_160], rax
0x18000a596  lea     rdx, _TraceLoggingMetadata
0x18000a59d  mov     [rsp+250h+EventDescriptor.Keyword], r9
0x18000a5a2  lea     rax, [rsp+250h+var_21C]
0x18000a5a7  mov     [rbp+150h+var_170], rax
0x18000a5ab  xor     r9d, r9d; RelatedActivityId
0x18000a5ae  mov     [rbp+150h+var_144], ebx
0x18000a5b1  lea     rax, [rsp+250h+var_220]
0x18000a5b6  mov     [rbp+150h+var_180], rax
0x18000a5ba  xor     r8d, r8d; ActivityId
0x18000a5bd  mov     [rbp+150h+var_158], 8
0x18000a5c5  lea     rax, [rsp+250h+var_218]
0x18000a5ca  mov     [rbp+150h+var_1A0], rax
0x18000a5ce  lea     rax, [rsp+250h+var_208]
0x18000a5d3  mov     [rbp+150h+var_1B0], rax
0x18000a5d7  lea     rax, [rsp+250h+var_200]
0x18000a5dc  mov     [rbp+150h+var_1C0], rax
0x18000a5e0  movzx   eax, cs:word_18004CAB4
0x18000a5e7  mov     dword ptr [rsp+250h+EventDescriptor.Level], eax
0x18000a5eb  mov     rax, [rcx+8]
0x18000a5ef  mov     qword ptr [rsp+250h+Str], rax
0x18000a5f4  mov     [rbp+150h+var_168], 4
0x18000a5fc  mov     [rbp+150h+var_178], 1
0x18000a604  mov     [rbp+150h+var_188], 10h
0x18000a60c  mov     [rbp+150h+var_198], 4
0x18000a614  mov     [rbp+150h+var_1A8], 8
0x18000a61c  mov     [rbp+150h+var_1B8], 8
0x18000a624  mov     dword ptr [rsp+250h+EventDescriptor.Id], 0B000000h
0x18000a62c  movzx   eax, word ptr [rax]
0x18000a62f  mov     [rsp+250h+var_1D8], eax
0x18000a633  lea     rax, word_18004CABE
0x18000a63a  mov     [rbp+150h+var_1D0], rax
0x18000a63e  lea     rax, _TraceLoggingMetadataEnd
0x18000a645  sub     eax, edx
0x18000a647  mov     [rsp+250h+var_1D4], 2
0x18000a64f  mov     [rbp+150h+var_1C8], 7Fh
0x18000a656  lea     rdx, [rsp+250h+EventDescriptor]; EventDescriptor
0x18000a65b  mov     [rbp+150h+var_1C4], 1
0x18000a662  mov     [rsp+250h+var_214], eax
0x18000a666  mov     eax, [rsp+250h+var_214]
0x18000a66a  mov     rcx, [rcx+20h]; RegHandle
0x18000a66e  lea     rax, [rsp+250h+Str]
0x18000a673  mov     [rsp+250h+UserData], rax; UserData
0x18000a678  mov     [rsp+250h+UserDataCount], 0Ah; UserDataCount
0x18000a680  call    cs:__imp_EventWriteTransfer
0x18000a686  mov     r13, [rsp+250h+var_28]
0x18000a68e  mov     r12, [rsp+250h+arg_10]
0x18000a696  mov     rcx, [rbp+150h+var_40]
0x18000a69d  xor     rcx, rsp; StackCookie
0x18000a6a0  call    __security_check_cookie
0x18000a6a5  add     rsp, 230h
0x18000a6ac  pop     r15
0x18000a6ae  pop     rdi
0x18000a6af  pop     rsi
0x18000a6b0  pop     rbx
0x18000a6b1  pop     rbp
0x18000a6b2  retn
```
