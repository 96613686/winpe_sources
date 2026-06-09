# IkeInitSendBuffers

- ea: `0x18002cc20`
- end: `0x18002d114`
- name: `IkeInitSendBuffers`
- size: `1268`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014b60`
- `0x18002d940`

## callees

- `0x18002cc20`
- `0x180050850`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ccb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ccfd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ccb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ccfd`
- `ntdll!EtwEventWriteTransfer` at `0x18002cde5`
- `ntdll!EtwEventWriteTransfer` at `0x18002cde5`
- `WS2_32!__imp_htons` at `0x18002cedb`
- `WS2_32!__imp_htons` at `0x18002d004`
- `WS2_32!__imp_htons` at `0x18002cedb`
- `WS2_32!__imp_htons` at `0x18002d004`

## pseudocode

```c
LPCRITICAL_SECTION __fastcall IkeInitSendBuffers(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        ULONG_PTR *a7,
        _DWORD *a8,
        _DWORD *a9)
{
  LPCRITICAL_SECTION v13; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v16; // rcx
  DWORD v17; // ecx
  char *v18; // rax
  const WCHAR *v19; // rdx
  __int64 v20; // rax
  int v22; // eax
  __int64 v23; // rbx
  const void *v24; // rdx
  size_t v25; // r8
  __int16 v26; // bx
  LPCRITICAL_SECTION result; // rax
  ULONG_PTR SpinCount; // rcx
  __int64 v29; // rbx
  size_t v30; // r8
  const void *v31; // rdx
  __int16 v32; // bx
  __int64 v33; // [rsp+40h] [rbp-79h] BYREF
  _DWORD v34[2]; // [rsp+48h] [rbp-71h] BYREF
  __int64 v35; // [rsp+50h] [rbp-69h]
  char *v36; // [rsp+60h] [rbp-59h] BYREF
  int v37; // [rsp+68h] [rbp-51h]
  int v38; // [rsp+6Ch] [rbp-4Dh]
  int *v39; // [rsp+70h] [rbp-49h]
  int v40; // [rsp+78h] [rbp-41h]
  int v41; // [rsp+7Ch] [rbp-3Dh]
  __int64 *v42; // [rsp+80h] [rbp-39h]
  __int64 v43; // [rsp+88h] [rbp-31h]
  const WCHAR *v44; // [rsp+90h] [rbp-29h]
  int v45; // [rsp+98h] [rbp-21h]
  int v46; // [rsp+9Ch] [rbp-1Dh]
  const char *v47; // [rsp+A0h] [rbp-19h]
  __int64 v48; // [rsp+A8h] [rbp-11h]

  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v13 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v13 = gIkeExtGlobals;
LABEL_9:
    v16 = 0;
    goto LABEL_10;
  }
  v16 = *Value;
  v13 = gIkeExtGlobals;
LABEL_10:
  v33 = v16;
  v42 = &v33;
  v43 = 8;
  if ( !v13 )
    goto LABEL_18;
  v17 = (DWORD)v13[86].LockSemaphore;
  if ( v17 == -1 )
    goto LABEL_18;
  v18 = (char *)TlsGetValue(v17);
  v19 = (const WCHAR *)(v18 + 8);
  if ( !v18 )
    v19 = 0;
  if ( v19 )
  {
    v20 = -1;
    while ( v19[++v20] != 0 )
      ;
    v22 = 2 * v20 + 2;
  }
  else
  {
LABEL_18:
    v19 = &LocaleName;
    v22 = 2;
  }
  v45 = v22;
  v44 = v19;
  v47 = "IkeInitSendBuffers";
  v34[1] = 5;
  v36 = off_180173280;
  v46 = 0;
  v48 = 19;
  v34[0] = 184549376;
  v35 = 1;
  v37 = *(unsigned __int16 *)off_180173280;
  v39 = &dword_180166EA4;
  v38 = 2;
  v40 = 45;
  v41 = 1;
  EtwEventWriteTransfer(qword_180173298, v34, 0, 0, 5, &v36);
LABEL_20:
  *(_DWORD *)a3 = *(_DWORD *)(a1 + 8);
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a1;
  *(_QWORD *)(a6 + 40) = a4;
  *(_DWORD *)(a6 + 24) = 1;
  *(_QWORD *)(a6 + 16) = a3;
  *a9 = 0;
  switch ( *(_BYTE *)a2 )
  {
    case 1:
    case 4:
    case 7:
      *a8 = 28;
      v29 = *(_QWORD *)(a6 + 40);
      v30 = 16;
      *(_QWORD *)a6 = a2 + 64;
      *(_DWORD *)(a6 + 8) = 16;
      *(_DWORD *)(a6 + 32) = 24;
      *(_QWORD *)v29 = 24;
      *(_DWORD *)(v29 + 8) = 0;
      *(_DWORD *)(v29 + 12) = 19;
      switch ( *(_BYTE *)a2 )
      {
        case 1:
        case 4:
        case 7:
          v31 = (const void *)(a2 + 8);
          v30 = 4;
          goto LABEL_34;
        case 5:
        case 6:
        case 8:
          v31 = (const void *)(a2 + 12);
LABEL_34:
          memcpy_0((void *)(v29 + 16), v31, v30);
          *(_DWORD *)(v29 + 20) = a5;
          switch ( *(_BYTE *)a2 )
          {
            case 1:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
              v32 = *(_WORD *)(a2 + 6);
              if ( v32 == htons(0x1F4u) )
              {
                result = gIkeExtGlobals;
                SpinCount = gIkeExtGlobals[71].SpinCount;
              }
              else
              {
                if ( *(_DWORD *)(a1 + 8) > 1u )
                {
                  *(_DWORD *)a3 = 4;
                  *(_QWORD *)(a3 + 8) = &IKE_4500_NULL_PAD_BUF;
                  *(_DWORD *)(a3 + 16) = *(_DWORD *)(a1 + 8);
                  *(_QWORD *)(a3 + 24) = *(_QWORD *)a1;
                  *(_DWORD *)(a6 + 24) = 2;
                  *a9 = 1;
                }
                result = gIkeExtGlobals;
                SpinCount = (ULONG_PTR)gIkeExtGlobals[72].DebugInfo;
              }
              goto LABEL_27;
            default:
              goto LABEL_40;
          }
        default:
          goto LABEL_40;
      }
    case 5:
    case 6:
    case 8:
      *a8 = 48;
      v23 = *(_QWORD *)(a6 + 40);
      *(_QWORD *)a6 = a2 + 64;
      *(_DWORD *)(a6 + 8) = 28;
      *(_DWORD *)(a6 + 32) = 40;
      *(_QWORD *)v23 = 36;
      *(_DWORD *)(v23 + 8) = 41;
      *(_DWORD *)(v23 + 12) = 19;
      switch ( *(_BYTE *)a2 )
      {
        case 1:
        case 4:
        case 7:
          v24 = (const void *)(a2 + 8);
          v25 = 4;
          goto LABEL_24;
        case 5:
        case 6:
        case 8:
          v24 = (const void *)(a2 + 12);
          v25 = 16;
LABEL_24:
          memcpy_0((void *)(v23 + 16), v24, v25);
          *(_DWORD *)(v23 + 32) = a5;
          switch ( *(_BYTE *)a2 )
          {
            case 1:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
              v26 = *(_WORD *)(a2 + 6);
              if ( v26 == htons(0x1F4u) )
              {
                result = gIkeExtGlobals;
                SpinCount = *(_QWORD *)&gIkeExtGlobals[72].LockCount;
              }
              else
              {
                if ( *(_DWORD *)(a1 + 8) > 1u )
                {
                  *(_DWORD *)a3 = 4;
                  *(_QWORD *)(a3 + 8) = &IKE_4500_NULL_PAD_BUF;
                  *(_DWORD *)(a3 + 16) = *(_DWORD *)(a1 + 8);
                  *(_QWORD *)(a3 + 24) = *(_QWORD *)a1;
                  *(_DWORD *)(a6 + 24) = 2;
                  *a9 = 1;
                }
                result = gIkeExtGlobals;
                SpinCount = (ULONG_PTR)gIkeExtGlobals[72].OwningThread;
              }
LABEL_27:
              *a7 = SpinCount;
              return result;
            default:
              goto LABEL_40;
          }
        default:
          goto LABEL_40;
      }
    default:
      break;
  }
LABEL_40:
  __fastfail(5u);
}

```

## disassembly

```asm
0x18002cc20  mov     [rsp-8+arg_0], rbx
0x18002cc25  push    rbp
0x18002cc26  push    rsi
0x18002cc27  push    rdi
0x18002cc28  push    r12
0x18002cc2a  push    r13
0x18002cc2c  push    r14
0x18002cc2e  push    r15
0x18002cc30  lea     rbp, [rsp-7]
0x18002cc35  sub     rsp, 0C0h
0x18002cc3c  mov     rax, cs:__security_cookie
0x18002cc43  xor     rax, rsp
0x18002cc46  mov     [rbp+37h+var_40], rax
0x18002cc4a  mov     rax, [rbp+37h+arg_40]
0x18002cc51  mov     r12, r9
0x18002cc54  mov     r14, [rbp+37h+arg_28]
0x18002cc58  mov     rsi, r8
0x18002cc5b  mov     r13, [rbp+37h+arg_30]
0x18002cc5f  mov     rdi, rdx
0x18002cc62  mov     rbx, [rbp+37h+arg_38]
0x18002cc66  mov     r15, rcx
0x18002cc69  mov     [rsp+0F0h+var_B8], rax
0x18002cc6e  mov     eax, cs:dword_180173278
0x18002cc74  cmp     eax, 5
0x18002cc77  jbe     loc_18002CDEB
0x18002cc7d  mov     rcx, cs:qword_180173290
0x18002cc84  mov     rax, cs:qword_180173288
0x18002cc8b  test    al, 1
0x18002cc8d  jz      loc_18002CDEB
0x18002cc93  mov     rax, rcx
0x18002cc96  and     eax, 1
0x18002cc99  cmp     rax, rcx
0x18002cc9c  jnz     loc_18002CDEB
0x18002cca2  mov     rax, cs:gIkeExtGlobals
0x18002cca9  test    rax, rax
0x18002ccac  jz      short loc_18002CCD7
0x18002ccae  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002ccb4  cmp     ecx, 0FFFFFFFFh
0x18002ccb7  jz      short loc_18002CCD7
0x18002ccb9  call    cs:__imp_TlsGetValue
0x18002ccbf  test    rax, rax
0x18002ccc2  jz      short loc_18002CCD0
0x18002ccc4  mov     rcx, [rax]
0x18002ccc7  mov     rax, cs:gIkeExtGlobals
0x18002ccce  jmp     short loc_18002CCD9
0x18002ccd0  mov     rax, cs:gIkeExtGlobals
0x18002ccd7  xor     ecx, ecx
0x18002ccd9  mov     [rbp+37h+var_B0], rcx
0x18002ccdd  lea     rcx, [rbp+37h+var_B0]
0x18002cce1  mov     [rbp+37h+var_70], rcx
0x18002cce5  mov     [rbp+37h+var_68], 8
0x18002cced  test    rax, rax
0x18002ccf0  jz      short loc_18002CD34
0x18002ccf2  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002ccf8  cmp     ecx, 0FFFFFFFFh
0x18002ccfb  jz      short loc_18002CD34
0x18002ccfd  call    cs:__imp_TlsGetValue
0x18002cd03  xor     ecx, ecx
0x18002cd05  test    rax, rax
0x18002cd08  lea     rdx, [rax+8]
0x18002cd0c  cmovz   rdx, rcx
0x18002cd10  test    rdx, rdx
0x18002cd13  jz      short loc_18002CD34
0x18002cd15  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002cd1c  nop     dword ptr [rax+00h]
0x18002cd20  cmp     [rdx+rax*2+2], cx
0x18002cd25  lea     rax, [rax+1]
0x18002cd29  jnz     short loc_18002CD20
0x18002cd2b  lea     eax, ds:2[rax*2]
0x18002cd32  jmp     short loc_18002CD40
0x18002cd34  lea     rdx, LocaleName
0x18002cd3b  mov     eax, 2
0x18002cd40  mov     [rbp+37h+var_58], eax
0x18002cd43  lea     rcx, _TraceLoggingMetadata
0x18002cd4a  mov     [rbp+37h+var_60], rdx
0x18002cd4e  lea     rax, aIkeinitsendbuf; "IkeInitSendBuffers"
0x18002cd55  mov     [rbp+37h+var_50], rax
0x18002cd59  lea     rdx, [rbp+37h+var_A8]
0x18002cd5d  movzx   eax, cs:word_180166E9A
0x18002cd64  xor     r9d, r9d
0x18002cd67  mov     [rbp+37h+var_A4], eax
0x18002cd6a  xor     r8d, r8d
0x18002cd6d  mov     rax, cs:off_180173280
0x18002cd74  mov     [rbp+37h+var_90], rax
0x18002cd78  mov     [rbp+37h+var_54], 0
0x18002cd7f  mov     [rbp+37h+var_48], 13h
0x18002cd87  mov     [rbp+37h+var_A8], 0B000000h
0x18002cd8e  mov     [rbp+37h+var_A0], 1
0x18002cd96  movzx   eax, word ptr [rax]
0x18002cd99  mov     [rbp+37h+var_88], eax
0x18002cd9c  lea     rax, dword_180166EA4
0x18002cda3  mov     [rbp+37h+var_80], rax
0x18002cda7  lea     rax, _TraceLoggingMetadataEnd
0x18002cdae  sub     eax, ecx
0x18002cdb0  mov     [rbp+37h+var_84], 2
0x18002cdb7  mov     [rbp+37h+var_78], 2Dh ; '-'
0x18002cdbe  mov     [rbp+37h+var_74], 1
0x18002cdc5  mov     [rsp+0F0h+var_C0], eax
0x18002cdc9  mov     eax, [rsp+0F0h+var_C0]
0x18002cdcd  mov     rcx, cs:qword_180173298
0x18002cdd4  lea     rax, [rbp+37h+var_90]
0x18002cdd8  mov     [rsp+0F0h+var_C8], rax
0x18002cddd  mov     [rsp+0F0h+var_D0], 5
0x18002cde5  call    cs:__imp_EtwEventWriteTransfer
0x18002cdeb  mov     eax, [r15+8]
0x18002cdef  mov     [rsi], eax
0x18002cdf1  mov     rax, [r15]
0x18002cdf4  mov     [rsi+8], rax
0x18002cdf8  mov     [r14+28h], r12
0x18002cdfc  mov     r12, [rsp+0F0h+var_B8]
0x18002ce01  mov     dword ptr [r14+18h], 1
0x18002ce09  mov     [r14+10h], rsi
0x18002ce0d  mov     dword ptr [r12], 0
0x18002ce15  movzx   eax, byte ptr [rdi]
0x18002ce18  dec     eax; switch 8 cases
0x18002ce1a  cmp     eax, 7
0x18002ce1d  ja      def_18002CE36; jumptable 000000018002CE36 default case, cases 2,3
0x18002ce23  cdqe
0x18002ce25  lea     rdx, __ImageBase
0x18002ce2c  mov     eax, ds:(jpt_18002CE36 - 180000000h)[rdx+rax*4]
0x18002ce33  add     rax, rdx
0x18002ce36  jmp     rax; switch jump
0x18002ce38  mov     dword ptr [rbx], 30h ; '0'; jumptable 000000018002CE36 cases 5,6,8
0x18002ce3e  lea     rax, [rdi+40h]
0x18002ce42  mov     rbx, [r14+28h]
0x18002ce46  mov     [r14], rax
0x18002ce49  mov     dword ptr [r14+8], 1Ch
0x18002ce51  mov     dword ptr [r14+20h], 28h ; '('
0x18002ce59  mov     qword ptr [rbx], 24h ; '$'
0x18002ce60  mov     dword ptr [rbx+8], 29h ; ')'
0x18002ce67  mov     dword ptr [rbx+0Ch], 13h
0x18002ce6e  movzx   eax, byte ptr [rdi]
0x18002ce71  dec     eax; switch 8 cases
0x18002ce73  cmp     eax, 7
0x18002ce76  ja      def_18002CE36; jumptable 000000018002CE36 default case, cases 2,3
0x18002ce7c  cdqe
0x18002ce7e  mov     ecx, ds:(jpt_18002CE88 - 180000000h)[rdx+rax*4]
0x18002ce85  add     rcx, rdx
0x18002ce88  jmp     rcx; switch jump
0x18002ce8a  lea     rdx, [rdi+8]; jumptable 000000018002CE88 cases 1,4,7
0x18002ce8e  mov     r8d, 4
0x18002ce94  jmp     short loc_18002CEA0
0x18002ce96  lea     rdx, [rdi+0Ch]; jumptable 000000018002CE88 cases 5,6,8
0x18002ce9a  mov     r8d, 10h; Size
0x18002cea0  lea     rcx, [rbx+10h]; void *
0x18002cea4  call    memcpy_0
0x18002cea9  mov     eax, [rbp+37h+arg_20]
0x18002ceac  mov     [rbx+20h], eax
0x18002ceaf  movzx   eax, byte ptr [rdi]
0x18002ceb2  dec     eax; switch 8 cases
0x18002ceb4  cmp     eax, 7
0x18002ceb7  ja      def_18002CE36; jumptable 000000018002CE36 default case, cases 2,3
0x18002cebd  lea     rdx, __ImageBase
0x18002cec4  cdqe
0x18002cec6  mov     ecx, ds:(jpt_18002CED0 - 180000000h)[rdx+rax*4]
0x18002cecd  add     rcx, rdx
0x18002ced0  jmp     rcx; switch jump
0x18002ced2  movzx   ebx, word ptr [rdi+6]; jumptable 000000018002CED0 cases 1,4-8
0x18002ced6  mov     ecx, 1F4h; hostshort
0x18002cedb  call    cs:__imp_htons
0x18002cee1  cmp     bx, ax
0x18002cee4  jnz     short loc_18002CF1F
0x18002cee6  mov     rax, cs:gIkeExtGlobals
0x18002ceed  mov     rcx, [rax+0B48h]
0x18002cef4  mov     [r13+0], rcx
0x18002cef8  mov     rcx, [rbp+37h+var_40]
0x18002cefc  xor     rcx, rsp; StackCookie
0x18002ceff  call    __security_check_cookie
0x18002cf04  mov     rbx, [rsp+0F0h+arg_0]
0x18002cf0c  add     rsp, 0C0h
0x18002cf13  pop     r15
0x18002cf15  pop     r14
0x18002cf17  pop     r13
0x18002cf19  pop     r12
0x18002cf1b  pop     rdi
0x18002cf1c  pop     rsi
0x18002cf1d  pop     rbp
0x18002cf1e  retn
0x18002cf1f  cmp     dword ptr [r15+8], 1
0x18002cf24  jbe     short loc_18002CF55
0x18002cf26  mov     dword ptr [rsi], 4
0x18002cf2c  lea     rax, IKE_4500_NULL_PAD_BUF
0x18002cf33  mov     [rsi+8], rax
0x18002cf37  mov     eax, [r15+8]
0x18002cf3b  mov     [rsi+10h], eax
0x18002cf3e  mov     rax, [r15]
0x18002cf41  mov     [rsi+18h], rax
0x18002cf45  mov     dword ptr [r14+18h], 2
0x18002cf4d  mov     dword ptr [r12], 1
0x18002cf55  mov     rax, cs:gIkeExtGlobals
0x18002cf5c  mov     rcx, [rax+0B50h]
0x18002cf63  jmp     short loc_18002CEF4
0x18002cf65  mov     dword ptr [rbx], 1Ch; jumptable 000000018002CE36 cases 1,4,7
0x18002cf6b  lea     rax, [rdi+40h]
0x18002cf6f  mov     rbx, [r14+28h]
0x18002cf73  mov     r8d, 10h; Size
0x18002cf79  mov     [r14], rax
0x18002cf7c  mov     [r14+8], r8d
0x18002cf80  mov     dword ptr [r14+20h], 18h
0x18002cf88  mov     qword ptr [rbx], 18h
0x18002cf8f  mov     dword ptr [rbx+8], 0
0x18002cf96  mov     dword ptr [rbx+0Ch], 13h
0x18002cf9d  movzx   eax, byte ptr [rdi]
0x18002cfa0  dec     eax; switch 8 cases
0x18002cfa2  cmp     eax, 7
0x18002cfa5  ja      def_18002CE36; jumptable 000000018002CE36 default case, cases 2,3
0x18002cfab  cdqe
0x18002cfad  mov     ecx, ds:(jpt_18002CFB7 - 180000000h)[rdx+rax*4]
0x18002cfb4  add     rcx, rdx
0x18002cfb7  jmp     rcx; switch jump
0x18002cfb9  lea     rdx, [rdi+8]; jumptable 000000018002CFB7 cases 1,4,7
0x18002cfbd  mov     r8d, 4
0x18002cfc3  jmp     short loc_18002CFC9
0x18002cfc5  lea     rdx, [rdi+0Ch]; jumptable 000000018002CFB7 cases 5,6,8
0x18002cfc9  lea     rcx, [rbx+10h]; void *
0x18002cfcd  call    memcpy_0
0x18002cfd2  mov     eax, [rbp+37h+arg_20]
0x18002cfd5  mov     [rbx+14h], eax
0x18002cfd8  movzx   eax, byte ptr [rdi]
0x18002cfdb  dec     eax; switch 8 cases
0x18002cfdd  cmp     eax, 7
0x18002cfe0  ja      def_18002CE36; jumptable 000000018002CE36 default case, cases 2,3
0x18002cfe6  lea     rdx, __ImageBase
0x18002cfed  cdqe
0x18002cfef  mov     ecx, ds:(jpt_18002CFF9 - 180000000h)[rdx+rax*4]
0x18002cff6  add     rcx, rdx
0x18002cff9  jmp     rcx; switch jump
0x18002cffb  movzx   ebx, word ptr [rdi+6]; jumptable 000000018002CFF9 cases 1,4-8
0x18002cfff  mov     ecx, 1F4h; hostshort
0x18002d004  call    cs:__imp_htons
0x18002d00a  cmp     bx, ax
0x18002d00d  jnz     short loc_18002D022
0x18002d00f  mov     rax, cs:gIkeExtGlobals
0x18002d016  mov     rcx, [rax+0B38h]
0x18002d01d  jmp     loc_18002CEF4
0x18002d022  cmp     dword ptr [r15+8], 1
0x18002d027  jbe     short loc_18002D058
0x18002d029  mov     dword ptr [rsi], 4
0x18002d02f  lea     rax, IKE_4500_NULL_PAD_BUF
0x18002d036  mov     [rsi+8], rax
0x18002d03a  mov     eax, [r15+8]
0x18002d03e  mov     [rsi+10h], eax
0x18002d041  mov     rax, [r15]
0x18002d044  mov     [rsi+18h], rax
0x18002d048  mov     dword ptr [r14+18h], 2
0x18002d050  mov     dword ptr [r12], 1
0x18002d058  mov     rax, cs:gIkeExtGlobals
0x18002d05f  mov     rcx, [rax+0B40h]
0x18002d066  jmp     loc_18002CEF4
0x18002d06b  mov     ecx, 5; jumptable 000000018002CE36 default case, cases 2,3
0x18002d070  int     29h; Win8: RtlFailFast(ecx)
```
