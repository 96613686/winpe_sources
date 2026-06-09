# SpAcquireCredentialsHandle

- ea: `0x180007a20`
- end: `0x180008175`
- name: `SpAcquireCredentialsHandle`
- size: `1877`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x180006c50`
- `0x180007700`
- `0x180007a20`
- `0x180008180`
- `0x180008d14`
- `0x18000afac`
- `0x18002ee7c`
- `0x18002f014`
- `0x180040bac`
- `0x18004b720`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d1a`
- `ntdll!RtlInitUnicodeString` at `0x180007aac`
- `ntdll!RtlInitUnicodeString` at `0x180007ab8`
- `ntdll!RtlInitUnicodeString` at `0x180007ac4`
- `ntdll!RtlInitUnicodeString` at `0x180007aac`
- `ntdll!RtlInitUnicodeString` at `0x180007ab8`
- `ntdll!RtlInitUnicodeString` at `0x180007ac4`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x180007c1f`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x180007c1f`
- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x180007b67`
- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x180007b67`

## pseudocode

```c
__int64 __fastcall SpAcquireCredentialsHandle(
        __int64 a1,
        unsigned int a2,
        struct _LUID *a3,
        void *a4,
        __int64 a5,
        unsigned __int64 a6,
        __int64 a7,
        __int64 a8)
{
  WCHAR *v11; // r15
  unsigned int v12; // r12d
  int v13; // eax
  int v14; // ebx
  LONG HighPart; // ecx
  DWORD LowPart; // eax
  int v17; // eax
  int v18; // eax
  _QWORD *v19; // r10
  PWSTR v20; // rax
  _BYTE *v21; // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  WCHAR *v26; // rax
  __int64 Length; // rax
  PWSTR Buffer; // rcx
  const void *v29; // rbx
  size_t v30; // rsi
  WCHAR *v31; // rax
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r9
  __int64 v38; // rdx
  HANDLE hObject; // [rsp+58h] [rbp-59h] BYREF
  __int64 v40; // [rsp+60h] [rbp-51h] BYREF
  struct _UNICODE_STRING v41; // [rsp+68h] [rbp-49h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-39h]
  struct _UNICODE_STRING v43; // [rsp+88h] [rbp-29h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-19h] BYREF
  struct _LUID v45[4]; // [rsp+A8h] [rbp-9h] BYREF
  unsigned int v46; // [rsp+100h] [rbp+4Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
  v46 = a2;
  memset(v45, 0, sizeof(v45));
  v40 = 0;
  hObject = 0;
  v11 = 0;
  v12 = 0;
  DestinationString = 0;
  v43 = 0;
  v41 = 0;
  *(_OWORD *)Src = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v43, 0);
  RtlInitUnicodeString(&v41, 0);
  if ( (a2 & 3) == 0 )
  {
    v14 = -2146893054;
    goto LABEL_17;
  }
  if ( a5 )
  {
    v14 = -2146893054;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v36 = 34;
    goto LABEL_73;
  }
  if ( a6 >= 2 )
  {
    v14 = -2146893054;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v36 = 35;
LABEL_73:
    v37 = 2148074242LL;
    goto LABEL_74;
  }
  v13 = ((__int64 (__fastcall *)(struct _LUID *))LsaFunctions->GetClientInfo)(v45);
  v14 = v13;
  if ( v13 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v36 = 36;
    v37 = (unsigned int)v13;
    goto LABEL_74;
  }
  HighPart = v45[0].HighPart;
  hObject = (HANDLE)v45[3];
  LowPart = v45[0].LowPart;
  if ( !a3 || !*(_QWORD *)a3 || *a3 == *(_QWORD *)v45 )
  {
    a3 = v45;
    goto LABEL_9;
  }
  if ( !LOBYTE(v45[2].LowPart) )
  {
    v14 = -1073741727;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v36 = 37;
    v37 = 3221225569LL;
    goto LABEL_74;
  }
  if ( *a3 == *(_QWORD *)v45 )
    goto LABEL_9;
  v23 = ((__int64 (__fastcall *)(struct _LUID *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(a3, &hObject);
  v14 = v23;
  if ( v23 >= 0 )
  {
    HighPart = v45[0].HighPart;
    LowPart = v45[0].LowPart;
LABEL_9:
    if ( BYTE2(v45[2].LowPart) )
    {
      v46 |= 0x10000000u;
      if ( (a2 & 2) != 0 && (LowPart != 996 || HighPart || a3->LowPart != 996 || a3->HighPart || a4) )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_96;
        v38 = 39;
        goto LABEL_95;
      }
    }
    if ( v45[2].HighPart <= 1 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_96;
      v38 = 40;
LABEL_95:
      WPP_SF_(v19[2], v38, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
      v19 = WPP_GLOBAL_Control;
LABEL_96:
      v14 = -2146893042;
      goto LABEL_18;
    }
    if ( a4 )
    {
      v14 = MsvpCaptureSuppliedCred(a4, &v46, &DestinationString, &v43, &v41);
      if ( v14 < 0 )
        goto LABEL_17;
    }
    if ( !v41.Length )
      goto LABEL_13;
    v12 = v41.Length + 2;
    v26 = (WCHAR *)NtLmAllocate(v12);
    v11 = v26;
    if ( !v26 )
    {
      v14 = -1073741670;
      goto LABEL_17;
    }
    memcpy_0(v26, v41.Buffer, v41.Length);
    v14 = NtLmDecodeSecret(v11, hObject);
    if ( v14 >= 0 )
    {
      Length = v41.Length;
      Buffer = v41.Buffer;
      if ( v41.Length )
      {
        do
        {
          *(_BYTE *)Buffer = 0;
          Buffer = (PWSTR)((char *)Buffer + 1);
          --Length;
        }
        while ( Length );
        Buffer = v41.Buffer;
      }
      NtLmFree(Buffer);
      v29 = Src[1];
      v41.Buffer = 0;
      *(_DWORD *)&v41.Length = 0;
      if ( Src[1] )
      {
        v30 = WORD1(Src[0]);
        v31 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)(WORD1(Src[0]));
        v41.Buffer = v31;
        if ( !v31 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
            v19 = WPP_GLOBAL_Control;
          }
          v14 = -1073741801;
          goto LABEL_18;
        }
        v41.Length = (USHORT)Src[0];
        v41.MaximumLength = v30;
        memcpy_0(v31, v29, v30);
      }
LABEL_13:
      v17 = LsaIGetSupplementalTokenInfo(hObject, &v40);
      v14 = v17;
      if ( v17 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_DDd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            WPP_9f54ae5c059a34c647826de37781d01b_Traceguids,
            (unsigned int)v45[0].HighPart,
            v45[0].LowPart,
            v17);
          goto LABEL_17;
        }
        goto LABEL_18;
      }
      v18 = SsprAcquireCredentialHandle(a3, hObject, a7, a8, (__int64)&v40, &v43, &DestinationString, &v41);
      v14 = v18;
      if ( v18 >= 0 )
      {
        v43.Buffer = 0;
        DestinationString.Buffer = 0;
        if ( v41.Buffer )
          v41.Buffer = 0;
        goto LABEL_17;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v36 = 42;
      v37 = (unsigned int)v18;
LABEL_74:
      WPP_SF_d(v19[2], v36, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids, v37);
    }
LABEL_17:
    v19 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DDDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, (unsigned int)v23, a3->HighPart, a3->LowPart);
    goto LABEL_17;
  }
LABEL_18:
  if ( hObject && hObject != (HANDLE)v45[3] )
  {
    CloseHandle(hObject);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v40 )
  {
    LsaIFreeSupplementalTokenInfo();
    v19 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    v32 = v12;
    v33 = v11;
    if ( v12 )
    {
      do
      {
        *(_BYTE *)v33 = 0;
        v33 = (WCHAR *)((char *)v33 + 1);
        --v32;
      }
      while ( v32 );
    }
    NtLmFree(v11);
    v19 = WPP_GLOBAL_Control;
  }
  v20 = v41.Buffer;
  if ( v41.Buffer )
  {
    v34 = v41.Length;
    if ( v41.Length )
    {
      do
      {
        *(_BYTE *)v20 = 0;
        v20 = (PWSTR)((char *)v20 + 1);
        --v34;
      }
      while ( v34 );
    }
    NtLmFree(v41.Buffer);
    v19 = WPP_GLOBAL_Control;
  }
  v21 = Src[1];
  if ( Src[1] )
  {
    v35 = LOWORD(Src[0]);
    if ( LOWORD(Src[0]) )
    {
      do
      {
        *v21++ = 0;
        --v35;
      }
      while ( v35 );
    }
    ((void (__fastcall *)(void *))LsaFunctions->FreePrivateHeap)(Src[1]);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v43.Buffer )
  {
    NtLmFree(v43.Buffer);
    v19 = WPP_GLOBAL_Control;
  }
  if ( DestinationString.Buffer )
  {
    NtLmFree(DestinationString.Buffer);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x100) != 0 )
    WPP_SF_d(v19[2], 43, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180007a20  mov     rax, rsp
0x180007a23  push    rbp
0x180007a24  lea     rbp, [rax-3Fh]
0x180007a28  sub     rsp, 0E0h
0x180007a2f  mov     [rax+18h], rsi
0x180007a33  mov     rsi, r9
0x180007a36  mov     [rax+20h], rdi
0x180007a3a  mov     rdi, r8
0x180007a3d  mov     [rax-10h], r12
0x180007a41  mov     [rax-18h], r13
0x180007a45  mov     [rax-20h], r14
0x180007a49  mov     r14d, edx
0x180007a4c  mov     [rax-28h], r15
0x180007a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a57  lea     rax, WPP_GLOBAL_Control
0x180007a5e  cmp     rcx, rax
0x180007a61  jnz     loc_180007C99
0x180007a67  xorps   xmm0, xmm0
0x180007a6a  mov     [rsp+0E0h+arg_0], rbx
0x180007a72  xor     r13d, r13d
0x180007a75  mov     [rbp+37h+arg_8], r14d
0x180007a79  xorps   xmm1, xmm1
0x180007a7c  mov     [rbp+37h+var_40.LowPart], r13d
0x180007a80  movups  xmmword ptr [rbp+37h+var_40.HighPart], xmm0
0x180007a84  xor     edx, edx; SourceString
0x180007a86  mov     [rbp+37h+var_88], r13
0x180007a8a  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180007a8e  mov     [rbp+37h+hObject], r13
0x180007a92  movups  xmmword ptr [rbp+7], xmm0
0x180007a96  mov     r15d, r13d
0x180007a99  mov     r12d, r13d
0x180007a9c  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x180007aa0  movups  xmmword ptr [rbp+37h+var_60.Length], xmm1
0x180007aa4  movups  xmmword ptr [rbp+37h+var_80.Length], xmm0
0x180007aa8  movups  xmmword ptr [rbp+37h+Src], xmm1
0x180007aac  call    cs:__imp_RtlInitUnicodeString
0x180007ab2  xor     edx, edx; SourceString
0x180007ab4  lea     rcx, [rbp+37h+var_60]; DestinationString
0x180007ab8  call    cs:__imp_RtlInitUnicodeString
0x180007abe  xor     edx, edx; SourceString
0x180007ac0  lea     rcx, [rbp+37h+var_80]; DestinationString
0x180007ac4  call    cs:__imp_RtlInitUnicodeString
0x180007aca  test    r14b, 3
0x180007ace  jz      loc_180007D10
0x180007ad4  cmp     [rbp+37h+arg_20], r12
0x180007ad8  jnz     loc_180007F74
0x180007ade  cmp     [rbp+37h+arg_28], 2
0x180007ae3  jnb     loc_180007FCC
0x180007ae9  mov     rax, cs:LsaFunctions
0x180007af0  lea     rcx, [rbp+37h+var_40]
0x180007af4  mov     rax, [rax+80h]
0x180007afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b00  mov     ebx, eax
0x180007b02  test    eax, eax
0x180007b04  js      loc_180007FF5
0x180007b0a  mov     rax, [rbp+37h+var_28]
0x180007b0e  mov     ecx, [rbp+37h+var_40.HighPart]
0x180007b11  mov     [rbp+37h+hObject], rax
0x180007b15  mov     eax, [rbp+37h+var_40.LowPart]
0x180007b18  test    rdi, rdi
0x180007b1b  jz      short loc_180007B31
0x180007b1d  mov     edx, [rdi]
0x180007b1f  test    edx, edx
0x180007b21  jnz     loc_180007D2C
0x180007b27  cmp     [rdi+4], r13d
0x180007b2b  jnz     loc_180007D2C
0x180007b31  lea     rdi, [rbp+37h+var_40]
0x180007b35  cmp     [rbp+9], r12b
0x180007b39  jnz     loc_180008071
0x180007b3f  cmp     [rbp+37h+var_2C], 1
0x180007b43  jle     loc_1800080E7
0x180007b49  test    rsi, rsi
0x180007b4c  jnz     loc_180007CE4
0x180007b52  movzx   eax, [rbp+37h+var_80.Length]
0x180007b56  test    ax, ax
0x180007b59  jnz     loc_180007E03
0x180007b5f  mov     rcx, [rbp+37h+hObject]
0x180007b63  lea     rdx, [rbp+37h+var_88]
0x180007b67  call    cs:__imp_LsaIGetSupplementalTokenInfo
0x180007b6d  mov     ebx, eax
0x180007b6f  test    eax, eax
0x180007b71  js      loc_180007DAA
0x180007b77  mov     r9d, [rbp+37h+arg_8]
0x180007b7b  lea     rax, [rbp+37h+var_80]
0x180007b7f  mov     rdx, [rbp+37h+hObject]; TokenHandle
0x180007b83  lea     r8, [rbp+37h+var_40]
0x180007b87  mov     [rsp+48h], rax; struct _UNICODE_STRING *
0x180007b8c  mov     rcx, rdi; struct _LUID *
0x180007b8f  lea     rax, [rbp+37h+DestinationString]
0x180007b93  mov     [rsp+0E0h+String2], rax; String2
0x180007b98  lea     rax, [rbp+37h+var_60]
0x180007b9c  mov     [rsp+0E0h+var_A8], rax; struct _UNICODE_STRING *
0x180007ba1  lea     rax, [rbp+37h+var_88]
0x180007ba5  mov     [rsp+0E0h+var_B0], rax; __int64
0x180007baa  mov     rax, [rbp+37h+arg_38]
0x180007bae  mov     [rsp+0E0h+var_B8], rax; __int64
0x180007bb3  mov     rax, [rbp+37h+arg_30]
0x180007bb7  mov     [rsp+0E0h+var_C0], rax; __int64
0x180007bbc  call    SsprAcquireCredentialHandle
0x180007bc1  mov     ebx, eax
0x180007bc3  test    eax, eax
0x180007bc5  js      loc_18000812C
0x180007bcb  mov     [rbp+37h+var_60.Buffer], r13
0x180007bcf  mov     [rbp+37h+DestinationString.Buffer], r13
0x180007bd3  cmp     [rbp+37h+var_80.Buffer], r13
0x180007bd7  jz      short loc_180007BDD
0x180007bd9  mov     [rbp+37h+var_80.Buffer], r13
0x180007bdd  lea     rsi, WPP_GLOBAL_Control
0x180007be4  mov     r10, cs:WPP_GLOBAL_Control
0x180007beb  mov     rcx, [rbp+37h+hObject]; hObject
0x180007bef  mov     r14, [rsp+0E0h+var_18]
0x180007bf7  mov     r13, [rsp+0E0h+var_10]
0x180007bff  mov     rdi, [rsp+0E0h+arg_18]
0x180007c07  test    rcx, rcx
0x180007c0a  jz      short loc_180007C16
0x180007c0c  cmp     rcx, [rbp+37h+var_28]
0x180007c10  jnz     loc_180007D1A
0x180007c16  mov     rcx, [rbp+37h+var_88]
0x180007c1a  test    rcx, rcx
0x180007c1d  jz      short loc_180007C2C
0x180007c1f  call    cs:__imp_LsaIFreeSupplementalTokenInfo
0x180007c25  mov     r10, cs:WPP_GLOBAL_Control
0x180007c2c  test    r15, r15
0x180007c2f  jnz     loc_180007EE4
0x180007c35  mov     rax, [rbp+37h+var_80.Buffer]
0x180007c39  mov     r15, [rsp+0E0h+var_20]
0x180007c41  mov     r12, [rsp+0D8h]
0x180007c49  test    rax, rax
0x180007c4c  jnz     loc_180007F10
0x180007c52  mov     rax, [rbp+37h+Src+8]
0x180007c56  test    rax, rax
0x180007c59  jnz     loc_180007F3B
0x180007c5f  mov     rcx, [rbp+37h+var_60.Buffer]
0x180007c63  test    rcx, rcx
0x180007c66  jnz     loc_180008153
0x180007c6c  mov     rcx, [rbp+37h+DestinationString.Buffer]
0x180007c70  test    rcx, rcx
0x180007c73  jnz     loc_180008164
0x180007c79  cmp     r10, rsi
0x180007c7c  mov     rsi, [rsp+0E0h+arg_10]
0x180007c84  jnz     short loc_180007CC0
0x180007c86  mov     eax, ebx
0x180007c88  mov     rbx, [rsp+0E0h+arg_0]
0x180007c90  add     rsp, 0E0h
0x180007c97  pop     rbp
0x180007c98  retn
0x180007c99  test    dword ptr [rcx+1Ch], 100h
0x180007ca0  jz      loc_180007A67
0x180007ca6  mov     rcx, [rcx+10h]
0x180007caa  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x180007cb1  mov     edx, 21h ; '!'
0x180007cb6  call    WPP_SF_
0x180007cbb  jmp     loc_180007A67
0x180007cc0  test    dword ptr [r10+1Ch], 100h
0x180007cc8  jz      short loc_180007C86
0x180007cca  mov     rcx, [r10+10h]
0x180007cce  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x180007cd5  mov     edx, 2Bh ; '+'
0x180007cda  mov     r9d, ebx
0x180007cdd  call    WPP_SF_d
0x180007ce2  jmp     short loc_180007C86
0x180007ce4  lea     rax, [rbp+37h+var_80]
0x180007ce8  mov     rcx, rsi; void *
0x180007ceb  lea     r9, [rbp+37h+var_60]; struct _UNICODE_STRING *
0x180007cef  mov     [rsp+0E0h+var_C0], rax; struct _UNICODE_STRING *
0x180007cf4  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x180007cf8  lea     rdx, [rbp+37h+arg_8]; unsigned int *
0x180007cfc  call    ?MsvpCaptureSuppliedCred@@YAJPEAXPEAKPEAU_UNICODE_STRING@@22@Z; MsvpCaptureSuppliedCred(void *,ulong *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180007d01  mov     ebx, eax
0x180007d03  test    eax, eax
0x180007d05  jns     loc_180007B52
0x180007d0b  jmp     loc_180007BDD
0x180007d10  mov     ebx, 80090302h
0x180007d15  jmp     loc_180007BDD
0x180007d1a  call    cs:__imp_CloseHandle
0x180007d20  mov     r10, cs:WPP_GLOBAL_Control
0x180007d27  jmp     loc_180007C16
0x180007d2c  cmp     edx, eax
0x180007d2e  jz      loc_180008021
0x180007d34  cmp     [rbp+7], r12b
0x180007d38  jz      loc_18000802F
0x180007d3e  cmp     edx, eax
0x180007d40  jz      loc_180007DF5
0x180007d46  mov     rax, cs:LsaFunctions
0x180007d4d  lea     rdx, [rbp+37h+hObject]
0x180007d51  mov     rcx, rdi
0x180007d54  mov     rax, [rax+170h]
0x180007d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d60  mov     ebx, eax
0x180007d62  test    eax, eax
0x180007d64  jns     loc_180008066
0x180007d6a  mov     r10, cs:WPP_GLOBAL_Control
0x180007d71  lea     rsi, WPP_GLOBAL_Control
0x180007d78  cmp     r10, rsi
0x180007d7b  jz      loc_180007BEB
0x180007d81  test    byte ptr [r10+1Ch], 1
0x180007d86  jz      loc_180007BEB
0x180007d8c  mov     eax, [rdi]
0x180007d8e  mov     r9d, ebx
0x180007d91  mov     rcx, [r10+10h]
0x180007d95  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180007d99  mov     eax, [rdi+4]
0x180007d9c  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180007da0  call    WPP_SF_DDDsd
0x180007da5  jmp     loc_180007BE4
0x180007daa  mov     r10, cs:WPP_GLOBAL_Control
0x180007db1  lea     rsi, WPP_GLOBAL_Control
0x180007db8  cmp     r10, rsi
0x180007dbb  jz      loc_180007BEB
0x180007dc1  test    byte ptr [r10+1Ch], 1
0x180007dc6  jz      loc_180007BEB
0x180007dcc  mov     r9d, [rbp+37h+var_40.HighPart]
0x180007dd0  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x180007dd7  mov     rcx, [r10+10h]
0x180007ddb  mov     edx, 29h ; ')'
0x180007de0  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180007de4  mov     eax, [rbp+37h+var_40.LowPart]
0x180007de7  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180007deb  call    WPP_SF_DDd
0x180007df0  jmp     loc_180007BE4
0x180007df5  cmp     [rdi+4], ecx
0x180007df8  jz      loc_180007B35
0x180007dfe  jmp     loc_180007D46
0x180007e03  lea     r12d, [rax+2]
0x180007e07  mov     ecx, r12d; uBytes
0x180007e0a  call    NtLmAllocate
0x180007e0f  mov     r15, rax
0x180007e12  test    rax, rax
0x180007e15  jz      loc_180008103
0x180007e1b  movzx   r8d, [rbp+37h+var_80.Length]; Size
0x180007e20  mov     rcx, rax; void *
0x180007e23  mov     rdx, [rbp+37h+var_80.Buffer]; Src
0x180007e27  call    memcpy_0
0x180007e2c  mov     rdx, [rbp+37h+hObject]; Token
0x180007e30  lea     r8, [rbp+37h+Src]
0x180007e34  mov     rcx, r15; pszProtectedCredentials
0x180007e37  call    NtLmDecodeSecret
0x180007e3c  mov     ebx, eax
0x180007e3e  test    eax, eax
0x180007e40  js      loc_180007BDD
0x180007e46  movzx   eax, [rbp+37h+var_80.Length]
0x180007e4a  mov     rcx, [rbp+37h+var_80.Buffer]
0x180007e4e  test    rax, rax
0x180007e51  jz      short loc_180007E64
0x180007e53  mov     [rcx], r13b
0x180007e56  lea     rcx, [rcx+1]
0x180007e5a  sub     rax, 1
0x180007e5e  jnz     short loc_180007E53
0x180007e60  mov     rcx, [rbp+37h+var_80.Buffer]
0x180007e64  call    NtLmFree
0x180007e69  mov     rbx, [rbp+37h+Src+8]
0x180007e6d  mov     [rbp+37h+var_80.Buffer], r13
0x180007e71  mov     dword ptr [rbp+37h+var_80.Length], r13d
0x180007e75  test    rbx, rbx
0x180007e78  jz      loc_180007B5F
0x180007e7e  mov     rax, cs:LsaFunctions
0x180007e85  movzx   esi, word ptr [rbp+37h+Src+2]
0x180007e89  mov     ecx, esi
0x180007e8b  mov     rax, [rax+180h]
0x180007e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e97  mov     [rbp+37h+var_80.Buffer], rax
0x180007e9b  test    rax, rax
0x180007e9e  jnz     loc_18000810D
0x180007ea4  mov     r10, cs:WPP_GLOBAL_Control
0x180007eab  lea     rsi, WPP_GLOBAL_Control
0x180007eb2  cmp     r10, rsi
0x180007eb5  jz      short loc_180007EDA
0x180007eb7  test    byte ptr [r10+1Ch], 1
0x180007ebc  jz      short loc_180007EDA
0x180007ebe  mov     rcx, [r10+10h]
0x180007ec2  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x180007ec9  mov     edx, 10h
0x180007ece  call    WPP_SF_
0x180007ed3  mov     r10, cs:WPP_GLOBAL_Control
0x180007eda  mov     ebx, 0C0000017h
0x180007edf  jmp     loc_180007BEB
0x180007ee4  mov     ecx, r12d
0x180007ee7  mov     rax, r15
0x180007eea  test    r12d, r12d
0x180007eed  jz      short loc_180007EFC
0x180007eef  mov     byte ptr [rax], 0
0x180007ef2  lea     rax, [rax+1]
0x180007ef6  sub     rcx, 1
0x180007efa  jnz     short loc_180007EEF
0x180007efc  mov     rcx, r15
0x180007eff  call    NtLmFree
0x180007f04  mov     r10, cs:WPP_GLOBAL_Control
0x180007f0b  jmp     loc_180007C35
0x180007f10  movzx   ecx, [rbp+37h+var_80.Length]
0x180007f14  test    rcx, rcx
0x180007f17  jz      short loc_180007F26
0x180007f19  mov     byte ptr [rax], 0
0x180007f1c  lea     rax, [rax+1]
0x180007f20  sub     rcx, 1
0x180007f24  jnz     short loc_180007F19
0x180007f26  mov     rcx, [rbp+37h+var_80.Buffer]
0x180007f2a  call    NtLmFree
0x180007f2f  mov     r10, cs:WPP_GLOBAL_Control
0x180007f36  jmp     loc_180007C52
0x180007f3b  movzx   ecx, word ptr [rbp+37h+Src]
  ... truncated ...
```
