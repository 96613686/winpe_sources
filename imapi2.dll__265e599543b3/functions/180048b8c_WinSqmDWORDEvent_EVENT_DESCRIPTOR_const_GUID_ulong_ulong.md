# _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)

- ea: `0x180048b8c`
- end: `0x180048cd3`
- name: `?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z`
- size: `327`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, struct _GUID *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180046bf4`
- `0x180047040`

## callees

- `0x180048b8c`
- `0x180048cdc`
- `0x180049880`
- `0x18004a010`

## string_xrefs

- `0x180048c75`: `WinSqmEventWrite`

## pseudocode

```c
void __fastcall _WinSqmDWORDEvent(const struct _EVENT_DESCRIPTOR *a1, struct _GUID *a2, int a3, int a4)
{
  unsigned int (__fastcall *v5)(__int64 *, struct _GUID *); // rax
  FARPROC Proc; // rax
  void (__fastcall *v7)(__int64 *, __int64, struct _GUID **); // rax
  FARPROC v8; // rax
  struct _GUID *v9; // [rsp+20h] [rbp-40h] BYREF
  __int128 v10; // [rsp+28h] [rbp-38h]
  __int128 v11; // [rsp+38h] [rbp-28h]
  __int64 v12; // [rsp+48h] [rbp-18h]
  int v13; // [rsp+80h] [rbp+20h] BYREF
  int v14; // [rsp+88h] [rbp+28h] BYREF

  v14 = a4;
  v13 = a3;
  v9 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( dword_180061C84 )
  {
    v5 = (unsigned int (__fastcall *)(__int64 *, struct _GUID *))qword_1800627E0;
    if ( !qword_1800627E0 )
    {
      Proc = _WinSqmGetProc("WinSqmEventEnabled");
      if ( !Proc )
      {
LABEL_11:
        dword_180061C84 = 0;
        return;
      }
      _InterlockedCompareExchange64(&qword_1800627E0, (signed __int64)Proc, 0);
      v5 = (unsigned int (__fastcall *)(__int64 *, struct _GUID *))qword_1800627E0;
    }
    if ( v5(SQM_SET_DWORD_V0, a2) )
    {
      *(_QWORD *)&v10 = 16;
      *(_QWORD *)&v11 = 4;
      if ( !a2 )
        a2 = &g_WinSqmGlobalSession;
      v12 = 4;
      *((_QWORD *)&v10 + 1) = &v13;
      *((_QWORD *)&v11 + 1) = &v14;
      v9 = a2;
      if ( dword_180061C84 )
      {
        v7 = (void (__fastcall *)(__int64 *, __int64, struct _GUID **))qword_1800627E8;
        if ( !qword_1800627E8 )
        {
          v8 = _WinSqmGetProc("WinSqmEventWrite");
          if ( !v8 )
            goto LABEL_11;
          _InterlockedCompareExchange64(&qword_1800627E8, (signed __int64)v8, 0);
          v7 = (void (__fastcall *)(__int64 *, __int64, struct _GUID **))qword_1800627E8;
        }
        v7(SQM_SET_DWORD_V0, 3, &v9);
      }
    }
  }
}

```

## disassembly

```asm
0x180048b8c  mov     [rsp-8+arg_0], rbx
0x180048b91  mov     [rsp-8+arg_18], r9d
0x180048b96  mov     [rsp-8+arg_10], r8d
0x180048b9b  push    rbp
0x180048b9c  mov     rbp, rsp
0x180048b9f  sub     rsp, 60h
0x180048ba3  mov     rax, cs:__security_cookie
0x180048baa  xor     rax, rsp
0x180048bad  mov     [rbp+var_10], rax
0x180048bb1  xor     eax, eax
0x180048bb3  mov     [rbp+var_40], 0
0x180048bbb  cmp     cs:dword_180061C84, eax
0x180048bc1  xorps   xmm0, xmm0
0x180048bc4  mov     rbx, rdx
0x180048bc7  mov     [rbp+var_18], rax
0x180048bcb  movups  [rbp+var_38], xmm0
0x180048bcf  movups  [rbp+var_28], xmm0
0x180048bd3  jz      loc_180048CBC
0x180048bd9  mov     rax, cs:qword_1800627E0
0x180048be0  test    rax, rax
0x180048be3  jnz     short loc_180048C0F
0x180048be5  lea     rcx, aWinsqmeventena; "WinSqmEventEnabled"
0x180048bec  call    ?_WinSqmGetProc@@YAP6A_JXZPEBD@Z; _WinSqmGetProc(char const *)
0x180048bf1  mov     rcx, rax
0x180048bf4  test    rax, rax
0x180048bf7  jz      loc_180048C89
0x180048bfd  xor     eax, eax
0x180048bff  lock cmpxchg cs:qword_1800627E0, rcx
0x180048c08  mov     rax, cs:qword_1800627E0
0x180048c0f  mov     rdx, rbx
0x180048c12  lea     rcx, SQM_SET_DWORD_V0
0x180048c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c1e  test    eax, eax
0x180048c20  jz      loc_180048CBC
0x180048c26  test    rbx, rbx
0x180048c29  mov     qword ptr [rbp+var_38], 10h
0x180048c31  lea     rax, ?g_WinSqmGlobalSession@@3U_GUID@@B; _GUID const g_WinSqmGlobalSession
0x180048c38  mov     qword ptr [rbp+var_28], 4
0x180048c40  cmovz   rbx, rax
0x180048c44  mov     [rbp+var_18], 4
0x180048c4c  cmp     cs:dword_180061C84, 0
0x180048c53  lea     rax, [rbp+arg_10]
0x180048c57  mov     qword ptr [rbp+var_38+8], rax
0x180048c5b  lea     rax, [rbp+arg_18]
0x180048c5f  mov     qword ptr [rbp+var_28+8], rax
0x180048c63  mov     [rbp+var_40], rbx
0x180048c67  jz      short loc_180048CBC
0x180048c69  mov     rax, cs:qword_1800627E8
0x180048c70  test    rax, rax
0x180048c73  jnz     short loc_180048CA7
0x180048c75  lea     rcx, aWinsqmeventwri; "WinSqmEventWrite"
0x180048c7c  call    ?_WinSqmGetProc@@YAP6A_JXZPEBD@Z; _WinSqmGetProc(char const *)
0x180048c81  mov     rcx, rax
0x180048c84  test    rax, rax
0x180048c87  jnz     short loc_180048C95
0x180048c89  mov     cs:dword_180061C84, 0
0x180048c93  jmp     short loc_180048CBC
0x180048c95  xor     eax, eax
0x180048c97  lock cmpxchg cs:qword_1800627E8, rcx
0x180048ca0  mov     rax, cs:qword_1800627E8
0x180048ca7  lea     r8, [rbp+var_40]
0x180048cab  mov     edx, 3
0x180048cb0  lea     rcx, SQM_SET_DWORD_V0
0x180048cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cbc  mov     rcx, [rbp+var_10]
0x180048cc0  xor     rcx, rsp; StackCookie
0x180048cc3  call    __security_check_cookie
0x180048cc8  mov     rbx, [rsp+60h+arg_0]
0x180048ccd  add     rsp, 60h
0x180048cd1  pop     rbp
0x180048cd2  retn
```
