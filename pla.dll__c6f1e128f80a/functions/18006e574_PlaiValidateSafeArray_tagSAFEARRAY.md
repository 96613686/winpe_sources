# PlaiValidateSafeArray(tagSAFEARRAY *)

- ea: `0x18006e574`
- end: `0x18006e7e7`
- name: `?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(SAFEARRAY *psa)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180065830`
- `0x18009e130`
- `0x1800c62d0`
- `0x1800ea3a0`
- `0x1800f12d0`
- `0x1800f6ee0`
- `0x180100440`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18006e574`
- `0x18013aee0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18006e648`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18006e648`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006e7c4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006e7c4`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18006e5ac`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18006e5ac`

## pseudocode

```c
__int64 __fastcall PlaiValidateSafeArray(SAFEARRAY *psa)
{
  HRESULT Vartype; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  int *v5; // r9
  int *v6; // rcx
  HRESULT v7; // eax
  __int64 v8; // rax
  ULONG i; // edx
  _WORD *v10; // r8
  __int64 v11; // rax
  VARTYPE pvt; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  HRESULT v15; // [rsp+80h] [rbp-80h] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v17[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v18[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v19[64]; // [rsp+190h] [rbp+90h] BYREF

  pvt = 0;
  ppvData = 0;
  Vartype = SafeArrayGetVartype(psa, &pvt);
  v3 = Vartype;
  if ( Vartype >= 0 )
  {
    if ( pvt != 8 )
      goto LABEL_28;
    v7 = SafeArrayAccessData(psa, &ppvData);
    v3 = v7;
    if ( v7 >= 0 )
    {
      for ( i = 0; i < psa->rgsabound[0].cElements; ++i )
      {
        v10 = (_WORD *)*((_QWORD *)ppvData + i);
        if ( !v10 || !*v10 )
        {
          v3 = -2147024809;
          v14 = -2147024809;
          v15 = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v19, 0x4000000000000800uLL);
            v11 = -1;
            do
              ++v11;
            while ( v19[v11] );
            goto LABEL_26;
          }
          break;
        }
      }
    }
    else
    {
      v15 = 0;
      v14 = v7;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v18, 0x4000000000000800uLL);
        v8 = -1;
        do
          ++v8;
        while ( v18[v8] );
LABEL_26:
        v5 = &v14;
        v6 = &v15;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v14 = 0;
    v15 = Vartype;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v17, 0x4000000000000800uLL);
      v4 = -1;
      do
        ++v4;
      while ( v17[v4] );
      v5 = &v15;
      v6 = &v14;
LABEL_27:
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v5, 4, qword_180147320, 1, v6, 4, "PlaiValidateSafeArray", 22);
    }
  }
LABEL_28:
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  return v3;
}

```

## disassembly

```asm
0x18006e574  push    rbp
0x18006e576  push    rbx
0x18006e577  push    rsi
0x18006e578  push    rdi
0x18006e579  lea     rbp, [rsp-128h]
0x18006e581  sub     rsp, 228h
0x18006e588  mov     rax, cs:__security_cookie
0x18006e58f  xor     rax, rsp
0x18006e592  mov     [rbp+140h+var_30], rax
0x18006e599  xor     esi, esi
0x18006e59b  lea     rdx, [rsp+240h+pvt]; pvt
0x18006e5a0  mov     [rsp+240h+pvt], si
0x18006e5a5  mov     rdi, rcx
0x18006e5a8  mov     [rbp+140h+ppvData], rsi
0x18006e5ac  call    cs:__imp_SafeArrayGetVartype
0x18006e5b2  mov     ebx, eax
0x18006e5b4  test    eax, eax
0x18006e5b6  jns     short loc_18006E631
0x18006e5b8  cmp     dword ptr cs:xmmword_180169738, esi
0x18006e5be  mov     [rsp+240h+var_1C8], esi
0x18006e5c2  mov     [rbp+140h+var_1C0], eax
0x18006e5c5  jz      loc_18006E7BB
0x18006e5cb  mov     rdx, 4000000000000800h; unsigned __int64
0x18006e5d5  test    qword ptr cs:xmmword_180169738+8, rdx
0x18006e5dc  jz      loc_18006E7BB
0x18006e5e2  mov     rax, cs:qword_180169748
0x18006e5e9  and     rax, rdx
0x18006e5ec  cmp     cs:qword_180169748, rax
0x18006e5f3  jnz     loc_18006E7BB
0x18006e5f9  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x18006e5fd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18006e602  lea     rcx, [rbp+140h+var_1B0]
0x18006e606  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e60a  inc     rax
0x18006e60d  cmp     [rcx+rax*2], si
0x18006e611  jnz     short loc_18006E60A
0x18006e613  lea     ecx, [rax+rax]
0x18006e616  add     rcx, 2
0x18006e61a  lea     rax, [rbp+140h+var_1B0]
0x18006e61e  mov     [rsp+240h+var_1E0], rcx
0x18006e623  lea     r9, [rbp+140h+var_1C0]
0x18006e627  lea     rcx, [rsp+240h+var_1C8]
0x18006e62c  jmp     loc_18006E761
0x18006e631  mov     eax, 8
0x18006e636  cmp     ax, [rsp+240h+pvt]
0x18006e63b  jnz     loc_18006E7BB
0x18006e641  lea     rdx, [rbp+140h+ppvData]; ppvData
0x18006e645  mov     rcx, rdi; psa
0x18006e648  call    cs:__imp_SafeArrayAccessData
0x18006e64e  mov     ebx, eax
0x18006e650  test    eax, eax
0x18006e652  jns     short loc_18006E6BB
0x18006e654  cmp     dword ptr cs:xmmword_180169738, esi
0x18006e65a  mov     [rbp+140h+var_1C0], esi
0x18006e65d  mov     [rsp+240h+var_1C8], eax
0x18006e661  jz      loc_18006E7BB
0x18006e667  mov     rdx, 4000000000000800h; unsigned __int64
0x18006e671  test    qword ptr cs:xmmword_180169738+8, rdx
0x18006e678  jz      loc_18006E7BB
0x18006e67e  mov     rax, cs:qword_180169748
0x18006e685  and     rax, rdx
0x18006e688  cmp     cs:qword_180169748, rax
0x18006e68f  jnz     loc_18006E7BB
0x18006e695  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x18006e699  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18006e69e  lea     rcx, [rbp+140h+var_130]
0x18006e6a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e6a6  inc     rax
0x18006e6a9  cmp     [rcx+rax*2], si
0x18006e6ad  jnz     short loc_18006E6A6
0x18006e6af  lea     ecx, [rax+rax]
0x18006e6b2  lea     rax, [rbp+140h+var_130]
0x18006e6b6  jmp     loc_18006E74F
0x18006e6bb  mov     edx, esi
0x18006e6bd  cmp     edx, [rdi+18h]
0x18006e6c0  jnb     loc_18006E7BB
0x18006e6c6  mov     rax, [rbp+140h+ppvData]
0x18006e6ca  mov     ecx, edx
0x18006e6cc  mov     r8, [rax+rcx*8]
0x18006e6d0  test    r8, r8
0x18006e6d3  jz      short loc_18006E6DF
0x18006e6d5  cmp     si, [r8]
0x18006e6d9  jz      short loc_18006E6DF
0x18006e6db  inc     edx
0x18006e6dd  jmp     short loc_18006E6BD
0x18006e6df  cmp     dword ptr cs:xmmword_180169738, esi
0x18006e6e5  mov     ebx, 80070057h
0x18006e6ea  mov     [rsp+240h+var_1C8], ebx
0x18006e6ee  mov     [rbp+140h+var_1C0], esi
0x18006e6f1  jz      loc_18006E7BB
0x18006e6f7  mov     rdx, 4000000000000800h; unsigned __int64
0x18006e701  test    qword ptr cs:xmmword_180169738+8, rdx
0x18006e708  jz      loc_18006E7BB
0x18006e70e  mov     rax, cs:qword_180169748
0x18006e715  and     rax, rdx
0x18006e718  cmp     cs:qword_180169748, rax
0x18006e71f  jnz     loc_18006E7BB
0x18006e725  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x18006e72c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18006e731  lea     rcx, [rbp+140h+var_B0]
0x18006e738  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e73c  inc     rax
0x18006e73f  cmp     [rcx+rax*2], si
0x18006e743  jnz     short loc_18006E73C
0x18006e745  lea     ecx, [rax+rax]
0x18006e748  lea     rax, [rbp+140h+var_B0]
0x18006e74f  add     rcx, 2
0x18006e753  lea     r9, [rsp+240h+var_1C8]
0x18006e758  mov     [rsp+240h+var_1E0], rcx
0x18006e75d  lea     rcx, [rbp+140h+var_1C0]
0x18006e761  mov     [rsp+240h+var_1E8], rax
0x18006e766  lea     rdx, PLA_EVENT_ERROR
0x18006e76d  mov     [rsp+240h+var_1F0], 16h
0x18006e776  lea     rax, aPlaivalidatesa; "PlaiValidateSafeArray"
0x18006e77d  mov     [rsp+240h+var_1F8], rax
0x18006e782  mov     eax, 4
0x18006e787  mov     [rsp+240h+var_200], rax
0x18006e78c  mov     [rsp+240h+var_208], rcx
0x18006e791  lea     rcx, qword_180147320
0x18006e798  mov     [rsp+240h+var_210], 1
0x18006e7a1  mov     [rsp+240h+var_218], rcx
0x18006e7a6  lea     r8d, [rax+1]
0x18006e7aa  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18006e7b1  mov     [rsp+240h+var_220], rax
0x18006e7b6  call    EventingWriteEvent
0x18006e7bb  cmp     [rbp+140h+ppvData], rsi
0x18006e7bf  jz      short loc_18006E7CA
0x18006e7c1  mov     rcx, rdi; psa
0x18006e7c4  call    cs:__imp_SafeArrayUnaccessData
0x18006e7ca  mov     eax, ebx
0x18006e7cc  mov     rcx, [rbp+140h+var_30]
0x18006e7d3  xor     rcx, rsp; StackCookie
0x18006e7d6  call    __security_check_cookie
0x18006e7db  add     rsp, 228h
0x18006e7e2  pop     rdi
0x18006e7e3  pop     rsi
0x18006e7e4  pop     rbx
0x18006e7e5  pop     rbp
0x18006e7e6  retn
```
