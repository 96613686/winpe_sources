# DiscpAddProviderContext

- ea: `0x180014888`
- end: `0x180014959`
- name: `DiscpAddProviderContext`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010ed4`
- `0x180016934`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180014888`
- `0x180014b08`

## import_xrefs

- `fwpuclnt!FwpmTransactionCommit0` at `0x180014929`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180014929`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x180014916`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x180014916`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800148f8`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800148f8`
- `fwpuclnt!FwpmTransactionAbort0` at `0x180014933`
- `fwpuclnt!FwpmTransactionAbort0` at `0x180014933`

## pseudocode

```c
__int64 __fastcall DiscpAddProviderContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  DWORD v6; // ebx
  FWPM_PROVIDER_CONTEXT0 providerContext; // [rsp+30h] [rbp-98h] BYREF

  memset_0(&providerContext, 0, sizeof(providerContext));
  v6 = DiscpBuildProviderContext(&providerContext.providerContextKey, a4, a5);
  if ( !v6 )
  {
    v6 = FwpmTransactionBegin0(DiscpEngineHandle, 0);
    if ( !v6 )
    {
      v6 = FwpmProviderContextAdd0(DiscpEngineHandle, &providerContext, 0, 0);
      if ( v6 )
        FwpmTransactionAbort0(DiscpEngineHandle);
      else
        return FwpmTransactionCommit0(DiscpEngineHandle);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180014888  push    rbx
0x18001488a  push    rbp
0x18001488b  push    rsi
0x18001488c  push    rdi
0x18001488d  push    r14
0x18001488f  sub     rsp, 0A0h
0x180014896  mov     rax, cs:__security_cookie
0x18001489d  xor     rax, rsp
0x1800148a0  mov     [rsp+0C8h+var_38], rax
0x1800148a8  mov     rbx, [rsp+0C8h+arg_20]
0x1800148b0  mov     rbp, rdx
0x1800148b3  xor     edx, edx; Val
0x1800148b5  mov     esi, r8d
0x1800148b8  mov     r14, rcx
0x1800148bb  mov     rdi, r9
0x1800148be  lea     rcx, [rsp+0C8h+providerContext]; void *
0x1800148c3  lea     r8d, [rdx+58h]; Size
0x1800148c7  call    memset_0
0x1800148cc  mov     r9d, esi
0x1800148cf  mov     [rsp+0C8h+var_A0], rbx; __int64
0x1800148d4  mov     r8, rbp
0x1800148d7  mov     [rsp+0C8h+var_A8], rdi; __int64
0x1800148dc  mov     rdx, r14
0x1800148df  lea     rcx, [rsp+0C8h+providerContext]; Uuid
0x1800148e4  call    DiscpBuildProviderContext
0x1800148e9  mov     ebx, eax
0x1800148eb  test    eax, eax
0x1800148ed  jnz     short loc_180014939
0x1800148ef  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x1800148f6  xor     edx, edx; flags
0x1800148f8  call    cs:__imp_FwpmTransactionBegin0
0x1800148fe  mov     ebx, eax
0x180014900  test    eax, eax
0x180014902  jnz     short loc_180014939
0x180014904  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x18001490b  lea     rdx, [rsp+0C8h+providerContext]; providerContext
0x180014910  xor     r9d, r9d; id
0x180014913  xor     r8d, r8d; sd
0x180014916  call    cs:__imp_FwpmProviderContextAdd0
0x18001491c  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180014923  mov     ebx, eax
0x180014925  test    eax, eax
0x180014927  jnz     short loc_180014933
0x180014929  call    cs:__imp_FwpmTransactionCommit0
0x18001492f  mov     ebx, eax
0x180014931  jmp     short loc_180014939
0x180014933  call    cs:__imp_FwpmTransactionAbort0
0x180014939  mov     eax, ebx
0x18001493b  mov     rcx, [rsp+0C8h+var_38]
0x180014943  xor     rcx, rsp; StackCookie
0x180014946  call    __security_check_cookie
0x18001494b  add     rsp, 0A0h
0x180014952  pop     r14
0x180014954  pop     rdi
0x180014955  pop     rsi
0x180014956  pop     rbp
0x180014957  pop     rbx
0x180014958  retn
```
