# DfsStore::LookupRoot(_UNICODE_STRING *,_UNICODE_STRING *,uchar,DfsRootFolder * *,ushort const *,uchar,uchar *)

- ea: `0x140038abc`
- end: `0x140038df8`
- name: `?LookupRoot@DfsStore@@QEAAKPEAU_UNICODE_STRING@@0EPEAPEAVDfsRootFolder@@PEBGEPEAE@Z`
- size: `828`
- prototype: `unsigned int __usercall@<eax>(DfsStore *__hidden this@<rcx>, PCUNICODE_STRING String2@<rdx>, struct _UNICODE_STRING *@<r8>, unsigned __int8@<r9b>, struct DfsRootFolder **, const unsigned __int16 *, unsigned __int8, unsigned __int8 *)`
- caller_count: `6`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c2bc`
- `0x14001ca58`
- `0x140021e40`
- `0x140022598`
- `0x1400378c8`
- `0x140045478`

## callees

- `0x14000bc18`
- `0x14000dcf8`
- `0x14000fca8`
- `0x14001e6d4`
- `0x140038abc`
- `0x1400582bc`
- `0x140058ce0`
- `0x140058db8`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140038bfd`
- `ntdll!RtlCompareUnicodeString` at `0x140038c49`
- `ntdll!RtlCompareUnicodeString` at `0x140038c69`
- `ntdll!RtlCompareUnicodeString` at `0x140038bfd`
- `ntdll!RtlCompareUnicodeString` at `0x140038c49`
- `ntdll!RtlCompareUnicodeString` at `0x140038c69`
- `ntdll!RtlInitUnicodeString` at `0x140038b4e`
- `ntdll!RtlInitUnicodeString` at `0x140038cb4`
- `ntdll!RtlInitUnicodeString` at `0x140038cc6`
- `ntdll!RtlInitUnicodeString` at `0x140038b4e`
- `ntdll!RtlInitUnicodeString` at `0x140038cb4`
- `ntdll!RtlInitUnicodeString` at `0x140038cc6`

## pseudocode

```c
__int64 __fastcall DfsStore::LookupRoot(
        DfsStore *this,
        PCUNICODE_STRING String2,
        struct _UNICODE_STRING *a3,
        char a4,
        struct DfsRootFolder **a5,
        const unsigned __int16 *a6,
        unsigned __int8 a7,
        unsigned __int8 *a8)
{
  __int64 v11; // rbx
  unsigned int v12; // edi
  unsigned int *v13; // rcx
  PWSTR Buffer; // rax
  PWSTR v15; // rax
  struct _UNICODE_STRING v17; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v18; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF

  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 14, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids, String2);
  }
  if ( a4 )
    DfsGetNetbiosName(String2, &DestinationString, 0);
  else
    RtlInitUnicodeString(&DestinationString, 0);
  DfsStore::AcquireStoreLock(this, a7);
  if ( a8 )
    *a8 = 0;
  v11 = *((_QWORD *)this + 7);
  v12 = 1168;
  if ( v11 )
  {
    v13 = pWppControl;
    do
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && v13
        && (v13[7] & 0x20) != 0
        && *((_BYTE *)v13 + 25) >= 3u )
      {
        WPP_SF_Z(*((_QWORD *)v13 + 2), 15, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids, v11 + 296);
        v13 = pWppControl;
      }
      if ( a4 )
      {
        if ( *(_BYTE *)(v11 + 216) )
        {
          if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(v11 + 280), &DestinationString, 1u) )
          {
LABEL_32:
            if ( !RtlCompareUnicodeString(a3, (PCUNICODE_STRING)(v11 + 296), 1u) )
            {
              v12 = 0;
              if ( a7 )
              {
                v12 = 183;
              }
              else if ( (*(_DWORD *)(v11 + 272) & 0x2000) != 0 )
              {
                v12 = 1168;
              }
              else
              {
                _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
                *a5 = (struct DfsRootFolder *)v11;
              }
              goto LABEL_41;
            }
          }
          v13 = pWppControl;
        }
      }
      else
      {
        if ( String2 && String2->Length )
        {
          Buffer = String2->Buffer;
          if ( Buffer && *Buffer )
          {
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(v11 + 432), String2, 1u) )
              goto LABEL_32;
            v13 = pWppControl;
          }
          if ( String2->Length )
          {
            v15 = String2->Buffer;
            if ( v15 )
            {
              if ( *v15 )
                goto LABEL_34;
            }
          }
        }
        if ( !*(_BYTE *)(v11 + 216) )
          goto LABEL_32;
      }
LABEL_34:
      v11 = *(_QWORD *)(v11 + 472);
    }
    while ( v11 != *((_QWORD *)this + 7) );
  }
  if ( a7 )
  {
    v17 = 0;
    v18 = 0;
    RtlInitUnicodeString(&v17, 0);
    RtlInitUnicodeString(&v18, 0);
    v12 = DfsCreateUnicodeString(&v17, String2);
    if ( !v12 )
    {
      v12 = DfsCreateUnicodeString(&v18, a3);
      if ( !v12 )
      {
        v12 = (*(__int64 (__fastcall **)(DfsStore *, PWSTR, PWSTR, const unsigned __int16 *, char, struct DfsRootFolder **))(*(_QWORD *)this + 72LL))(
                this,
                v17.Buffer,
                v18.Buffer,
                a6,
                a4,
                a5);
        if ( !v12 )
          *a8 = 1;
      }
    }
    DfsFreeUnicodeString(&v17);
    DfsFreeUnicodeString(&v18);
  }
LABEL_41:
  DfsStore::ReleaseStoreLock(this, a7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (v12 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_ZqD(
      *((_QWORD *)pWppControl + 2),
      16,
      (unsigned int)WPP_417794ce451139ef3a777c1a55d669e5_Traceguids,
      (_DWORD)a3,
      v11,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x140038abc  mov     rax, rsp
0x140038abf  mov     [rax+8], rbx
0x140038ac3  mov     [rax+10h], rsi
0x140038ac7  mov     [rax+20h], r9b
0x140038acb  mov     [rax+18h], r8
0x140038acf  push    rbp
0x140038ad0  push    rdi
0x140038ad1  push    r12
0x140038ad3  push    r13
0x140038ad5  push    r14
0x140038ad7  mov     rbp, rsp
0x140038ada  sub     rsp, 70h
0x140038ade  xorps   xmm0, xmm0
0x140038ae1  mov     bl, r9b
0x140038ae4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140038ae8  mov     rsi, rdx
0x140038aeb  mov     r13, rcx
0x140038aee  lea     rax, WPP_GLOBAL_Control
0x140038af5  mov     r14d, 20h ; ' '
0x140038afb  cmp     cs:WPP_GLOBAL_Control, rax
0x140038b02  jz      short loc_140038B33
0x140038b04  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038b0b  test    rcx, rcx
0x140038b0e  jz      short loc_140038B33
0x140038b10  test    [rcx+1Ch], r14b
0x140038b14  jz      short loc_140038B33
0x140038b16  cmp     byte ptr [rcx+19h], 3
0x140038b1a  jb      short loc_140038B33
0x140038b1c  mov     rcx, [rcx+10h]
0x140038b20  lea     edx, [r14-12h]
0x140038b24  mov     r9, rsi
0x140038b27  lea     r8, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids
0x140038b2e  call    WPP_SF_Z
0x140038b33  test    bl, bl
0x140038b35  jz      short loc_140038B48
0x140038b37  xor     r8d, r8d
0x140038b3a  lea     rdx, [rbp+DestinationString]
0x140038b3e  mov     rcx, rsi
0x140038b41  call    DfsGetNetbiosName
0x140038b46  jmp     short loc_140038B5A
0x140038b48  xor     edx, edx; SourceString
0x140038b4a  lea     rcx, [rbp+DestinationString]; DestinationString
0x140038b4e  call    cs:__imp_RtlInitUnicodeString
0x140038b55  nop     dword ptr [rax+rax+00h]
0x140038b5a  mov     dl, [rbp+arg_30]; unsigned __int8
0x140038b5d  mov     rcx, r13; this
0x140038b60  call    ?AcquireStoreLock@DfsStore@@QEAAXE@Z; DfsStore::AcquireStoreLock(uchar)
0x140038b65  mov     r12, [rbp+arg_38]
0x140038b69  xor     edx, edx
0x140038b6b  test    r12, r12
0x140038b6e  jz      short loc_140038B74
0x140038b70  mov     [r12], dl
0x140038b74  mov     rbx, [r13+38h]
0x140038b78  mov     edi, 490h
0x140038b7d  test    rbx, rbx
0x140038b80  jz      loc_140038C97
0x140038b86  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038b8d  lea     rax, WPP_GLOBAL_Control
0x140038b94  cmp     cs:WPP_GLOBAL_Control, rax
0x140038b9b  jz      short loc_140038BD3
0x140038b9d  test    rcx, rcx
0x140038ba0  jz      short loc_140038BD3
0x140038ba2  test    [rcx+1Ch], r14b
0x140038ba6  jz      short loc_140038BD3
0x140038ba8  cmp     byte ptr [rcx+19h], 3
0x140038bac  jb      short loc_140038BD3
0x140038bae  mov     rcx, [rcx+10h]
0x140038bb2  lea     r9, [rbx+128h]
0x140038bb9  mov     edx, 0Fh
0x140038bbe  lea     r8, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids
0x140038bc5  call    WPP_SF_Z
0x140038bca  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038bd1  xor     edx, edx
0x140038bd3  cmp     [rbp+arg_18], dl
0x140038bd6  jnz     short loc_140038C33
0x140038bd8  test    rsi, rsi
0x140038bdb  jz      short loc_140038C29
0x140038bdd  cmp     [rsi], dx
0x140038be0  jz      short loc_140038C29
0x140038be2  mov     rax, [rsi+8]
0x140038be6  test    rax, rax
0x140038be9  jz      short loc_140038C16
0x140038beb  cmp     [rax], dx
0x140038bee  jz      short loc_140038C16
0x140038bf0  lea     rcx, [rbx+1B0h]; String1
0x140038bf7  mov     r8b, 1; CaseInsensitive
0x140038bfa  mov     rdx, rsi; String2
0x140038bfd  call    cs:__imp_RtlCompareUnicodeString
0x140038c04  nop     dword ptr [rax+rax+00h]
0x140038c09  xor     edx, edx
0x140038c0b  test    eax, eax
0x140038c0d  jz      short loc_140038C5B
0x140038c0f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038c16  cmp     [rsi], dx
0x140038c19  jz      short loc_140038C29
0x140038c1b  mov     rax, [rsi+8]
0x140038c1f  test    rax, rax
0x140038c22  jz      short loc_140038C29
0x140038c24  cmp     [rax], dx
0x140038c27  jnz     short loc_140038C86
0x140038c29  cmp     [rbx+0D8h], dl
0x140038c2f  jnz     short loc_140038C86
0x140038c31  jmp     short loc_140038C5B
0x140038c33  cmp     [rbx+0D8h], dl
0x140038c39  jz      short loc_140038C86
0x140038c3b  lea     rcx, [rbx+118h]; String1
0x140038c42  mov     r8b, 1; CaseInsensitive
0x140038c45  lea     rdx, [rbp+DestinationString]; String2
0x140038c49  call    cs:__imp_RtlCompareUnicodeString
0x140038c50  nop     dword ptr [rax+rax+00h]
0x140038c55  xor     edx, edx
0x140038c57  test    eax, eax
0x140038c59  jnz     short loc_140038C7F
0x140038c5b  mov     rcx, [rbp+String1]; String1
0x140038c5f  lea     rdx, [rbx+128h]; String2
0x140038c66  mov     r8b, 1; CaseInsensitive
0x140038c69  call    cs:__imp_RtlCompareUnicodeString
0x140038c70  nop     dword ptr [rax+rax+00h]
0x140038c75  xor     edx, edx
0x140038c77  test    eax, eax
0x140038c79  jz      loc_140038DC1
0x140038c7f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038c86  mov     rbx, [rbx+1D8h]
0x140038c8d  cmp     rbx, [r13+38h]
0x140038c91  jnz     loc_140038B8D
0x140038c97  cmp     [rbp+arg_30], dl
0x140038c9a  jz      loc_140038D40
0x140038ca0  xorps   xmm0, xmm0
0x140038ca3  lea     rcx, [rbp+var_30]; DestinationString
0x140038ca7  xorps   xmm1, xmm1
0x140038caa  xor     edx, edx; SourceString
0x140038cac  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x140038cb0  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x140038cb4  call    cs:__imp_RtlInitUnicodeString
0x140038cbb  nop     dword ptr [rax+rax+00h]
0x140038cc0  xor     edx, edx; SourceString
0x140038cc2  lea     rcx, [rbp+var_20]; DestinationString
0x140038cc6  call    cs:__imp_RtlInitUnicodeString
0x140038ccd  nop     dword ptr [rax+rax+00h]
0x140038cd2  mov     rdx, rsi
0x140038cd5  lea     rcx, [rbp+var_30]
0x140038cd9  call    DfsCreateUnicodeString
0x140038cde  mov     edi, eax
0x140038ce0  test    eax, eax
0x140038ce2  jnz     short loc_140038D2E
0x140038ce4  mov     rdx, [rbp+String1]
0x140038ce8  lea     rcx, [rbp+var_20]
0x140038cec  call    DfsCreateUnicodeString
0x140038cf1  mov     edi, eax
0x140038cf3  test    eax, eax
0x140038cf5  jnz     short loc_140038D2E
0x140038cf7  mov     rcx, [rbp+arg_20]
0x140038cfb  mov     rax, [r13+0]
0x140038cff  mov     r9, [rbp+arg_28]
0x140038d03  mov     r8, [rbp+var_20.Buffer]
0x140038d07  mov     rdx, [rbp+var_30.Buffer]
0x140038d0b  mov     rax, [rax+48h]
0x140038d0f  mov     [rsp+70h+var_48], rcx
0x140038d14  mov     cl, [rbp+arg_18]
0x140038d17  mov     byte ptr [rsp+70h+var_50], cl
0x140038d1b  mov     rcx, r13
0x140038d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d23  mov     edi, eax
0x140038d25  test    eax, eax
0x140038d27  jnz     short loc_140038D2E
0x140038d29  mov     byte ptr [r12], 1
0x140038d2e  lea     rcx, [rbp+var_30]
0x140038d32  call    DfsFreeUnicodeString
0x140038d37  lea     rcx, [rbp+var_20]
0x140038d3b  call    DfsFreeUnicodeString
0x140038d40  mov     dl, [rbp+arg_30]; unsigned __int8
0x140038d43  mov     rcx, r13; this
0x140038d46  call    ?ReleaseStoreLock@DfsStore@@QEAAXE@Z; DfsStore::ReleaseStoreLock(uchar)
0x140038d4b  lea     rax, WPP_GLOBAL_Control
0x140038d52  cmp     cs:WPP_GLOBAL_Control, rax
0x140038d59  jz      short loc_140038DA5
0x140038d5b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038d62  test    rcx, rcx
0x140038d65  jz      short loc_140038DA5
0x140038d67  mov     eax, edi
0x140038d69  neg     eax
0x140038d6b  sbb     edx, edx
0x140038d6d  and     edx, 0FFFFFFECh
0x140038d70  add     edx, 1Fh
0x140038d73  bts     r14d, edx
0x140038d77  test    [rcx+1Ch], r14d
0x140038d7b  jz      short loc_140038DA5
0x140038d7d  cmp     byte ptr [rcx+19h], 3
0x140038d81  jb      short loc_140038DA5
0x140038d83  mov     r9, [rbp+String1]
0x140038d87  lea     r8, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids
0x140038d8e  mov     rcx, [rcx+10h]
0x140038d92  mov     edx, 10h
0x140038d97  mov     dword ptr [rsp+70h+var_48], edi
0x140038d9b  mov     [rsp+70h+var_50], rbx
0x140038da0  call    WPP_SF_ZqD
0x140038da5  lea     r11, [rsp+70h+var_s0]
0x140038daa  mov     eax, edi
0x140038dac  mov     rbx, [r11+30h]
0x140038db0  mov     rsi, [r11+38h]
0x140038db4  mov     rsp, r11
0x140038db7  pop     r14
0x140038db9  pop     r13
0x140038dbb  pop     r12
0x140038dbd  pop     rdi
0x140038dbe  pop     rbp
0x140038dbf  retn
0x140038dc1  mov     edi, edx
0x140038dc3  cmp     [rbp+arg_30], dl
0x140038dc6  jz      short loc_140038DD2
0x140038dc8  mov     edi, 0B7h
0x140038dcd  jmp     loc_140038D40
0x140038dd2  test    dword ptr [rbx+110h], 2000h
0x140038ddc  jnz     short loc_140038DEE
0x140038dde  lock inc dword ptr [rbx+8]
0x140038de2  mov     rax, [rbp+arg_20]
0x140038de6  mov     [rax], rbx
0x140038de9  jmp     loc_140038D40
0x140038dee  mov     edi, 490h
0x140038df3  jmp     loc_140038D40
```
