# Enumerator::RemoveNamed<IFolderAction>(tagVARIANT,long (IFolderAction::*)(ushort * *))

- ea: `0x180067960`
- end: `0x180067cbf`
- name: `??$RemoveNamed@UIFolderAction@@@Enumerator@@QEAAJUtagVARIANT@@P8IFolderAction@@EAAJPEAPEAG@Z@Z`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ec7f0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180067960`
- `0x1801237d8`
- `0x18013ae8e`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067c7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067a38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067a38`
- `OLEAUT32!__imp_VariantClear` at `0x180067c33`
- `OLEAUT32!__imp_VariantClear` at `0x180067c33`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180067b44`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180067b44`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067c8c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067c8c`

## string_xrefs

- `0x180067993`: `Enumerator::RemoveNamed`
- `0x180067be0`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<IFolderAction>(__int64 a1, __int128 *a2, __int64 a3)
{
  __int64 v5; // xmm1_8
  int v6; // eax
  unsigned int v7; // r14d
  __int64 v8; // rax
  SAFEARRAY **v9; // r15
  HRESULT v10; // eax
  __int64 v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  unsigned int v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  __int128 v19; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v21[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v22[64]; // [rsp+130h] [rbp+30h] BYREF

  v16 = *(_DWORD *)(a1 + 56);
  v15 = 0;
  ppvData = 0;
  v18 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::RemoveNamed", 24, &v18, 8, &v16, 4);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v5 = *((_QWORD *)a2 + 2);
  v19 = *a2;
  v20 = v5;
  v6 = Enumerator::GetIndex<IFolderAction>(a1, &v19, a3, &v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = (SAFEARRAY **)(a1 + 64);
    v10 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v12 = v15;
      v13 = 3LL * v15;
      VariantClear((VARIANTARG *)ppvData + v15);
      memmove_0((char *)ppvData + 8 * v13, (char *)ppvData + 24 * v12 + 24, 24LL * (*(_DWORD *)(a1 + 76) - v12 - 1));
      *((_WORD *)ppvData + 12 * (unsigned int)--*(_DWORD *)(a1 + 76)) = 0;
    }
    else
    {
      v16 = 0;
      v15 = v10;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v22, 0x4000000000000800uLL);
        v11 = -1;
        do
          ++v11;
        while ( v22[v11] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v15, 4, byte_180147320, 1, &v16, 4);
      }
    }
  }
  else
  {
    v16 = 0;
    v15 = v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v21, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v21[v8] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v15, 4, byte_180147320, 1, &v16, 4);
    }
    v9 = (SAFEARRAY **)(a1 + 64);
  }
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v9);
  return v7;
}

```

## disassembly

```asm
0x180067960  mov     [rsp-8+arg_10], rbx
0x180067965  push    rbp
0x180067966  push    rsi
0x180067967  push    rdi
0x180067968  push    r12
0x18006796a  push    r13
0x18006796c  push    r14
0x18006796e  push    r15
0x180067970  lea     rbp, [rsp-0C0h]
0x180067978  sub     rsp, 1C0h
0x18006797f  mov     rax, cs:__security_cookie
0x180067986  xor     rax, rsp
0x180067989  mov     [rbp+0F0h+var_40], rax
0x180067990  mov     eax, [rcx+38h]
0x180067993  lea     r15, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x18006799a  xor     r12d, r12d
0x18006799d  mov     [rsp+1F0h+var_178], eax
0x1800679a1  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800679a8  mov     rbx, rdx
0x1800679ab  mov     rsi, rcx
0x1800679ae  mov     [rsp+1F0h+var_180], r12d
0x1800679b3  mov     [rbp+0F0h+ppvData], r12
0x1800679b7  lea     edi, [r12+4]
0x1800679bc  mov     [rbp+0F0h+var_168], rcx
0x1800679c0  lea     r13d, [r12+18h]
0x1800679c5  jz      short loc_180067A2E
0x1800679c7  mov     rdx, 4000000000000400h
0x1800679d1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800679d8  jz      short loc_180067A2E
0x1800679da  mov     rax, cs:qword_180169748
0x1800679e1  and     rax, rdx
0x1800679e4  cmp     cs:qword_180169748, rax
0x1800679eb  jnz     short loc_180067A2E
0x1800679ed  mov     [rsp+1F0h+var_1B0], rdi
0x1800679f2  lea     rax, [rsp+1F0h+var_178]
0x1800679f7  mov     [rsp+1F0h+var_1B8], rax
0x1800679fc  lea     r8d, [r12+3]
0x180067a01  lea     rax, [rbp+0F0h+var_168]
0x180067a05  mov     [rsp+1F0h+var_1C0], 8
0x180067a0e  mov     [rsp+1F0h+var_1C8], rax
0x180067a13  lea     rdx, PLA_EVENT_METHOD
0x180067a1a  mov     r9, r15
0x180067a1d  mov     [rsp+1F0h+var_1D0], r13
0x180067a22  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180067a29  call    EventingWriteEvent
0x180067a2e  cmp     [rsi+8], r12d
0x180067a32  jz      short loc_180067A3E
0x180067a34  lea     rcx, [rsi+10h]; lpCriticalSection
0x180067a38  call    cs:__imp_EnterCriticalSection
0x180067a3e  movaps  xmm0, xmmword ptr [rbx]
0x180067a41  lea     r9, [rsp+1F0h+var_180]
0x180067a46  movsd   xmm1, qword ptr [rbx+10h]
0x180067a4b  lea     rdx, [rbp+0F0h+var_160]
0x180067a4f  mov     rcx, rsi
0x180067a52  movaps  [rbp+0F0h+var_160], xmm0
0x180067a56  movsd   [rbp+0F0h+var_150], xmm1
0x180067a5b  call    ??$GetIndex@UIFolderAction@@@Enumerator@@IEAAJUtagVARIANT@@P8IFolderAction@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IFolderAction>(tagVARIANT,long (IFolderAction::*)(ushort * *),ulong *)
0x180067a60  mov     r14d, eax
0x180067a63  test    eax, eax
0x180067a65  jns     loc_180067B39
0x180067a6b  cmp     dword ptr cs:xmmword_180169738, r12d
0x180067a72  mov     [rsp+1F0h+var_178], r12d
0x180067a77  mov     [rsp+1F0h+var_180], eax
0x180067a7b  jz      loc_180067B30
0x180067a81  mov     rdx, 4000000000000800h; unsigned __int64
0x180067a8b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180067a92  jz      loc_180067B30
0x180067a98  mov     rax, cs:qword_180169748
0x180067a9f  and     rax, rdx
0x180067aa2  cmp     cs:qword_180169748, rax
0x180067aa9  jnz     loc_180067B30
0x180067aaf  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x180067ab3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180067ab8  lea     rcx, [rbp+0F0h+var_140]
0x180067abc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180067ac0  inc     rax
0x180067ac3  cmp     [rcx+rax*2], r12w
0x180067ac8  jnz     short loc_180067AC0
0x180067aca  lea     ecx, [rax+rax]
0x180067acd  mov     r8d, 5
0x180067ad3  add     rcx, 2
0x180067ad7  lea     rax, [rbp+0F0h+var_140]
0x180067adb  mov     [rsp+1F0h+var_190], rcx
0x180067ae0  lea     r9, [rsp+1F0h+var_180]
0x180067ae5  mov     [rsp+1F0h+var_198], rax
0x180067aea  lea     rdx, PLA_EVENT_ERROR
0x180067af1  mov     [rsp+1F0h+var_1A0], r13
0x180067af6  lea     rax, [rsp+1F0h+var_178]
0x180067afb  mov     [rsp+1F0h+var_1A8], r15
0x180067b00  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180067b07  mov     [rsp+1F0h+var_1B0], rdi
0x180067b0c  mov     [rsp+1F0h+var_1B8], rax
0x180067b11  lea     rax, byte_180147320
0x180067b18  mov     [rsp+1F0h+var_1C0], 1
0x180067b21  mov     [rsp+1F0h+var_1C8], rax
0x180067b26  mov     [rsp+1F0h+var_1D0], rdi
0x180067b2b  call    EventingWriteEvent
0x180067b30  lea     r15, [rsi+40h]
0x180067b34  jmp     loc_180067C73
0x180067b39  lea     r15, [rsi+40h]
0x180067b3d  mov     rcx, [r15]; psa
0x180067b40  lea     rdx, [rbp+0F0h+ppvData]; ppvData
0x180067b44  call    cs:__imp_SafeArrayAccessData
0x180067b4a  mov     r14d, eax
0x180067b4d  test    eax, eax
0x180067b4f  jns     loc_180067C23
0x180067b55  cmp     dword ptr cs:xmmword_180169738, r12d
0x180067b5c  mov     [rsp+1F0h+var_178], r12d
0x180067b61  mov     [rsp+1F0h+var_180], eax
0x180067b65  jz      loc_180067C73
0x180067b6b  mov     rdx, 4000000000000800h; unsigned __int64
0x180067b75  test    qword ptr cs:xmmword_180169738+8, rdx
0x180067b7c  jz      loc_180067C73
0x180067b82  mov     rax, cs:qword_180169748
0x180067b89  and     rax, rdx
0x180067b8c  cmp     cs:qword_180169748, rax
0x180067b93  jnz     loc_180067C73
0x180067b99  lea     rcx, [rbp+0F0h+var_C0]; unsigned __int16 *
0x180067b9d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180067ba2  lea     rcx, [rbp+0F0h+var_C0]
0x180067ba6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180067baa  inc     rax
0x180067bad  cmp     [rcx+rax*2], r12w
0x180067bb2  jnz     short loc_180067BAA
0x180067bb4  lea     ecx, [rax+rax]
0x180067bb7  mov     r8d, 5
0x180067bbd  add     rcx, 2
0x180067bc1  lea     rax, [rbp+0F0h+var_C0]
0x180067bc5  mov     [rsp+1F0h+var_190], rcx
0x180067bca  lea     r9, [rsp+1F0h+var_180]
0x180067bcf  mov     [rsp+1F0h+var_198], rax
0x180067bd4  lea     rdx, PLA_EVENT_ERROR
0x180067bdb  mov     [rsp+1F0h+var_1A0], r13
0x180067be0  lea     rax, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x180067be7  mov     [rsp+1F0h+var_1A8], rax
0x180067bec  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180067bf3  mov     [rsp+1F0h+var_1B0], rdi
0x180067bf8  lea     rax, [rsp+1F0h+var_178]
0x180067bfd  mov     [rsp+1F0h+var_1B8], rax
0x180067c02  lea     rax, byte_180147320
0x180067c09  mov     [rsp+1F0h+var_1C0], 1
0x180067c12  mov     [rsp+1F0h+var_1C8], rax
0x180067c17  mov     [rsp+1F0h+var_1D0], rdi
0x180067c1c  call    EventingWriteEvent
0x180067c21  jmp     short loc_180067C73
0x180067c23  mov     rax, [rbp+0F0h+ppvData]
0x180067c27  mov     ebx, [rsp+1F0h+var_180]
0x180067c2b  lea     rdi, [rbx+rbx*2]
0x180067c2f  lea     rcx, [rax+rdi*8]; pvarg
0x180067c33  call    cs:__imp_VariantClear
0x180067c39  mov     eax, [rsi+4Ch]
0x180067c3c  mov     rcx, [rbp+0F0h+ppvData]
0x180067c40  sub     eax, ebx
0x180067c42  dec     eax
0x180067c44  lea     r8, [rax+rax*2]
0x180067c48  lea     eax, [rbx+1]
0x180067c4b  shl     r8, 3; Size
0x180067c4f  lea     rax, [rax+rax*2]
0x180067c53  lea     rdx, [rcx+rax*8]; Src
0x180067c57  lea     rcx, [rcx+rdi*8]; void *
0x180067c5b  call    memmove_0
0x180067c60  dec     dword ptr [rsi+4Ch]
0x180067c63  mov     eax, [rsi+4Ch]
0x180067c66  lea     r8, [rax+rax*2]
0x180067c6a  mov     rax, [rbp+0F0h+ppvData]
0x180067c6e  mov     [rax+r8*8], r12w
0x180067c73  cmp     [rsi+8], r12d
0x180067c77  jz      short loc_180067C83
0x180067c79  lea     rcx, [rsi+10h]; lpCriticalSection
0x180067c7d  call    cs:__imp_LeaveCriticalSection
0x180067c83  cmp     [rbp+0F0h+ppvData], r12
0x180067c87  jz      short loc_180067C92
0x180067c89  mov     rcx, [r15]; psa
0x180067c8c  call    cs:__imp_SafeArrayUnaccessData
0x180067c92  mov     eax, r14d
0x180067c95  mov     rcx, [rbp+0F0h+var_40]
0x180067c9c  xor     rcx, rsp; StackCookie
0x180067c9f  call    __security_check_cookie
0x180067ca4  mov     rbx, [rsp+1F0h+arg_10]
0x180067cac  add     rsp, 1C0h
0x180067cb3  pop     r15
0x180067cb5  pop     r14
0x180067cb7  pop     r13
0x180067cb9  pop     r12
0x180067cbb  pop     rdi
0x180067cbc  pop     rsi
0x180067cbd  pop     rbp
0x180067cbe  retn
```
