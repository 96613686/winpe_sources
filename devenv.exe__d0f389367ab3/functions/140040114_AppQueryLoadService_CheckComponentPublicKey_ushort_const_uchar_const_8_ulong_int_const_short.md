# AppQueryLoadService::CheckComponentPublicKey(ushort const *,uchar const (*)[8],ulong,int const *,short *)

- ea: `0x140040114`
- end: `0x1400402ec`
- name: `?CheckComponentPublicKey@AppQueryLoadService@@IEAAJPEBGPEAY07$$CBEKPEBHPEAF@Z`
- size: `472`
- prototype: `__int64 __usercall@<rax>(AppQueryLoadService *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int8 (*)[8]@<r8>, unsigned int@<r9d>, const int *, __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140040010`

## callees

- `0x140001020`
- `0x140008488`
- `0x14000a720`
- `0x140033ab0`
- `0x140040114`
- `0x1400402ec`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14004020b`
- `OLEAUT32!__imp_SysAllocString` at `0x14004024a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004020b`
- `OLEAUT32!__imp_SysAllocString` at `0x14004024a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004023b`
- `OLEAUT32!__imp_SysFreeString` at `0x140040293`
- `OLEAUT32!__imp_SysFreeString` at `0x14004023b`
- `OLEAUT32!__imp_SysFreeString` at `0x140040293`
- `mscoree!StrongNameFreeBuffer` at `0x1400402a6`
- `mscoree!StrongNameFreeBuffer` at `0x1400402b5`
- `mscoree!StrongNameFreeBuffer` at `0x1400402a6`
- `mscoree!StrongNameFreeBuffer` at `0x1400402b5`
- `mscoree!StrongNameSignatureVerificationEx` at `0x1400401f0`
- `mscoree!StrongNameSignatureVerificationEx` at `0x1400401f0`
- `mscoree!StrongNameErrorInfo` at `0x140040260`
- `mscoree!StrongNameErrorInfo` at `0x140040260`
- `mscoree!StrongNameTokenFromAssemblyEx` at `0x14004017b`
- `mscoree!StrongNameTokenFromAssemblyEx` at `0x14004017b`

## string_xrefs

- `0x140040224`: `CheckComponentPublicKey SignatureVerification failed; `
- `0x14004026e`: `CheckComponentPublicKey failed; `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppQueryLoadService::CheckComponentPublicKey(
        AppQueryLoadService *this,
        const unsigned __int16 *a2,
        const unsigned __int8 (*a3)[8],
        unsigned int a4,
        const int *a5,
        __int16 *a6)
{
  int v10; // edi
  int v11; // edx
  BSTR v12; // rax
  OLECHAR *v13; // rbx
  OLECHAR *v14; // rbx
  DWORD v15; // eax
  ULONG *pcbPublicKeyBlob; // [rsp+20h] [rbp-40h]
  const unsigned __int16 *v18; // [rsp+28h] [rbp-38h]
  int v19[2]; // [rsp+30h] [rbp-30h] BYREF
  BYTE *ppbStrongNameToken; // [rsp+38h] [rbp-28h] BYREF
  BYTE *ppbPublicKeyBlob; // [rsp+40h] [rbp-20h] BYREF
  BOOLEAN pfWasVerified[4]; // [rsp+48h] [rbp-18h] BYREF
  ULONG pcbStrongNameToken; // [rsp+4Ch] [rbp-14h] BYREF
  ULONG v24; // [rsp+50h] [rbp-10h] BYREF

  v10 = 0;
  pcbStrongNameToken = 0;
  v24 = 0;
  ppbStrongNameToken = 0;
  ppbPublicKeyBlob = 0;
  *a6 = 0;
  if ( StrongNameTokenFromAssemblyEx(a2, &ppbStrongNameToken, &pcbStrongNameToken, &ppbPublicKeyBlob, &v24)
    && pcbStrongNameToken
    && ppbStrongNameToken )
  {
    v11 = 0;
    if ( a4 )
    {
      while ( pcbStrongNameToken != 8 || *(_QWORD *)ppbStrongNameToken != *(_QWORD *)&(*a3)[8 * v11] )
      {
        if ( ++v11 >= a4 )
          goto LABEL_16;
      }
      v10 = AppQueryLoadService::InDelaySignedBuild(this, v19);
      if ( v10 >= 0 )
      {
        if ( StrongNameSignatureVerificationEx(a2, v19[0] == 0, pfWasVerified) )
        {
          *a6 = -1;
          goto LABEL_16;
        }
        v12 = SysAllocString(L"Microsoft Visual Studio Appid Stub");
        v13 = v12;
        *(_QWORD *)v19 = v12;
        if ( v12 )
        {
          ActivityLog::LogEntryPath(
            (ActivityLog *)2,
            (int)v12,
            L"CheckComponentPublicKey SignatureVerification failed; ",
            a2,
            (const unsigned __int16 *)pcbPublicKeyBlob);
          SysFreeString(v13);
          goto LABEL_16;
        }
LABEL_21:
        ATL::AtlThrowImpl(-2147024882);
      }
    }
  }
  else
  {
    v14 = SysAllocString(L"Microsoft Visual Studio Appid Stub");
    *(_QWORD *)v19 = v14;
    if ( !v14 )
      goto LABEL_21;
    v15 = StrongNameErrorInfo();
    ActivityLog::LogEntryHrPath(
      (ActivityLog *)2,
      (int)v14,
      L"CheckComponentPublicKey failed; ",
      (const unsigned __int16 *)v15,
      (__int64)a2,
      v18);
    SysFreeString(v14);
    *a6 = 0;
  }
LABEL_16:
  if ( ppbStrongNameToken )
    StrongNameFreeBuffer(ppbStrongNameToken);
  if ( ppbPublicKeyBlob )
    StrongNameFreeBuffer(ppbPublicKeyBlob);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140040114  mov     [rsp-38h+arg_10], rbx
0x140040119  push    rbp
0x14004011a  push    rsi
0x14004011b  push    rdi
0x14004011c  push    r12
0x14004011e  push    r13
0x140040120  push    r14
0x140040122  push    r15
0x140040124  mov     rbp, rsp
0x140040127  sub     rsp, 60h
0x14004012b  mov     rax, cs:__security_cookie
0x140040132  xor     rax, rsp
0x140040135  mov     [rbp+var_8], rax
0x140040139  mov     ebx, r9d
0x14004013c  mov     r12, r8
0x14004013f  mov     rsi, rdx
0x140040142  mov     r15, rcx
0x140040145  mov     r14, [rbp+arg_28]
0x140040149  xor     r13d, r13d
0x14004014c  mov     edi, r13d
0x14004014f  mov     [rbp+pcbStrongNameToken], r13d
0x140040153  mov     [rbp+var_10], r13d
0x140040157  mov     [rbp+ppbStrongNameToken], r13
0x14004015b  mov     [rbp+ppbPublicKeyBlob], r13
0x14004015f  mov     [r14], r13w
0x140040163  lea     rax, [rbp+var_10]
0x140040167  mov     [rsp+60h+pcbPublicKeyBlob], rax; unsigned __int16 *
0x14004016c  lea     r9, [rbp+ppbPublicKeyBlob]; ppbPublicKeyBlob
0x140040170  lea     r8, [rbp+pcbStrongNameToken]; pcbStrongNameToken
0x140040174  lea     rdx, [rbp+ppbStrongNameToken]; ppbStrongNameToken
0x140040178  mov     rcx, rsi; wszFilePath
0x14004017b  call    cs:__imp_StrongNameTokenFromAssemblyEx
0x140040181  test    al, al
0x140040183  jz      loc_140040243
0x140040189  mov     r8d, [rbp+pcbStrongNameToken]
0x14004018d  test    r8d, r8d
0x140040190  jz      loc_140040243
0x140040196  cmp     [rbp+ppbStrongNameToken], r13
0x14004019a  jz      loc_140040243
0x1400401a0  mov     edx, r13d
0x1400401a3  test    ebx, ebx
0x1400401a5  jz      loc_14004029D
0x1400401ab  mov     r9d, edx
0x1400401ae  cmp     r8d, 8
0x1400401b2  jnz     short loc_1400401C1
0x1400401b4  mov     rax, [rbp+ppbStrongNameToken]
0x1400401b8  mov     rcx, [rax]
0x1400401bb  cmp     rcx, [r12+r9*8]
0x1400401bf  jz      short loc_1400401CC
0x1400401c1  inc     edx
0x1400401c3  cmp     edx, ebx
0x1400401c5  jb      short loc_1400401AB
0x1400401c7  jmp     loc_14004029D
0x1400401cc  lea     rdx, [rbp+var_30]; int *
0x1400401d0  mov     rcx, r15; this
0x1400401d3  call    ?InDelaySignedBuild@AppQueryLoadService@@AEAAJPEAH@Z; AppQueryLoadService::InDelaySignedBuild(int *)
0x1400401d8  mov     edi, eax
0x1400401da  test    eax, eax
0x1400401dc  js      loc_14004029D
0x1400401e2  cmp     [rbp+var_30], r13d
0x1400401e6  setz    dl; fForceVerification
0x1400401e9  lea     r8, [rbp+pfWasVerified]; pfWasVerified
0x1400401ed  mov     rcx, rsi; wszFilePath
0x1400401f0  call    cs:__imp_StrongNameSignatureVerificationEx
0x1400401f6  test    al, al
0x1400401f8  jz      short loc_140040204
0x1400401fa  or      word ptr [r14], 0FFFFh
0x1400401ff  jmp     loc_14004029D
0x140040204  lea     rcx, aMicrosoftVisua_1; "Microsoft Visual Studio Appid Stub"
0x14004020b  call    cs:__imp_SysAllocString
0x140040211  mov     rbx, rax
0x140040214  mov     qword ptr [rbp+var_30], rax
0x140040218  test    rax, rax
0x14004021b  jz      loc_1400402E1
0x140040221  mov     r9, rsi; unsigned __int16 *
0x140040224  lea     r8, aCheckcomponent_0; "CheckComponentPublicKey SignatureVerifi"...
0x14004022b  mov     rdx, rax; int
0x14004022e  mov     ecx, 2; this
0x140040233  call    ?LogEntryPath@ActivityLog@@YAJHPEBG00@Z; ActivityLog::LogEntryPath(int,ushort const *,ushort const *,ushort const *)
0x140040238  mov     rcx, rbx; bstrString
0x14004023b  call    cs:__imp_SysFreeString
0x140040241  jmp     short loc_14004029D
0x140040243  lea     rcx, aMicrosoftVisua_1; "Microsoft Visual Studio Appid Stub"
0x14004024a  call    cs:__imp_SysAllocString
0x140040250  mov     rbx, rax
0x140040253  mov     qword ptr [rbp+var_30], rax
0x140040257  test    rax, rax
0x14004025a  jz      loc_1400402E1
0x140040260  call    cs:__imp_StrongNameErrorInfo
0x140040266  mov     r9d, eax; unsigned __int16 *
0x140040269  mov     [rsp+60h+pcbPublicKeyBlob], rsi; __int64
0x14004026e  lea     r8, aCheckcomponent; "CheckComponentPublicKey failed; "
0x140040275  mov     rdx, rbx; int
0x140040278  mov     ecx, 2; this
0x14004027d  call    ?LogEntryHrPath@ActivityLog@@YAJHPEBG0J0@Z; ActivityLog::LogEntryHrPath(int,ushort const *,ushort const *,long,ushort const *)
0x140040282  nop
0x140040283  nop     dword ptr [rax+00h]
0x140040287  nop     word ptr [rax+rax+00000000h]
0x140040290  mov     rcx, rbx; bstrString
0x140040293  call    cs:__imp_SysFreeString
0x140040299  mov     [r14], r13w
0x14004029d  mov     rcx, [rbp+ppbStrongNameToken]; pbMemory
0x1400402a1  test    rcx, rcx
0x1400402a4  jz      short loc_1400402AC
0x1400402a6  call    cs:__imp_StrongNameFreeBuffer
0x1400402ac  mov     rcx, [rbp+ppbPublicKeyBlob]; pbMemory
0x1400402b0  test    rcx, rcx
0x1400402b3  jz      short loc_1400402BB
0x1400402b5  call    cs:__imp_StrongNameFreeBuffer
0x1400402bb  mov     eax, edi
0x1400402bd  mov     rcx, [rbp+var_8]
0x1400402c1  xor     rcx, rsp; StackCookie
0x1400402c4  call    __security_check_cookie
0x1400402c9  mov     rbx, [rsp+60h+arg_10]
0x1400402d1  add     rsp, 60h
0x1400402d5  pop     r15
0x1400402d7  pop     r14
0x1400402d9  pop     r13
0x1400402db  pop     r12
0x1400402dd  pop     rdi
0x1400402de  pop     rsi
0x1400402df  pop     rbp
0x1400402e0  retn
0x1400402e1  mov     ecx, 8007000Eh; int
0x1400402e6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
