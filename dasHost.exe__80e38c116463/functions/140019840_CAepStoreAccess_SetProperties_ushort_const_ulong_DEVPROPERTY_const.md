# CAepStoreAccess::SetProperties(ushort const *,ulong,_DEVPROPERTY const *)

- ea: `0x140019840`
- end: `0x14001993a`
- name: `?SetProperties@CAepStoreAccess@@UEAAJPEBGKPEBU_DEVPROPERTY@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(CAepStoreAccess *this, unsigned __int16 *, int, const struct _DEVPROPERTY *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140009090`
- `0x1400194f4`
- `0x140019840`
- `0x140019940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019907`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019907`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019894`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019894`
- `RPCRT4!NdrClientCall3` at `0x1400198fa`
- `RPCRT4!NdrClientCall3` at `0x1400198fa`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::SetProperties(
        CAepStoreAccess *this,
        unsigned __int16 *a2,
        int a3,
        const struct _DEVPROPERTY *a4)
{
  int AepId; // ebx
  int *v8; // rax
  int v10; // [rsp+30h] [rbp-58h]
  void *v11; // [rsp+40h] [rbp-48h] BYREF

  v11 = 0;
  if ( a2 && a3 && a4 )
  {
    AepId = DafMakeAepId(*((unsigned __int16 **)this + 3), a2);
    if ( AepId >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      if ( *((_DWORD *)this + 8) )
      {
        AepId = CAepStoreAccess::GetDasRpcBinding(this, &v11);
        if ( AepId >= 0 )
        {
          v8 = &dword_14002438C;
          if ( *((_QWORD *)this + 2) )
            v8 = (int *)*((_QWORD *)this + 2);
          v10 = a3;
          AepId = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&AepStoreAccess_ProxyInfo,
                                  2u,
                                  0,
                                  v11,
                                  0,
                                  v8,
                                  v10,
                                  a4).Pointer;
        }
      }
      else
      {
        AepId = -2140930029;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)AepId;
}

```

## disassembly

```asm
0x140019840  mov     rax, rsp
0x140019843  push    rbx
0x140019844  push    rbp
0x140019845  push    rsi
0x140019846  push    rdi
0x140019847  push    r14
0x140019849  push    r15
0x14001984b  sub     rsp, 58h
0x14001984f  mov     r14, r9
0x140019852  mov     r15d, r8d
0x140019855  mov     rsi, rcx
0x140019858  xor     edi, edi
0x14001985a  mov     [rax+10h], rdi
0x14001985e  mov     [rax-48h], rdi
0x140019862  test    rdx, rdx
0x140019865  jz      loc_140019919
0x14001986b  test    r8d, r8d
0x14001986e  jz      loc_140019919
0x140019874  test    r9, r9
0x140019877  jz      loc_140019919
0x14001987d  lea     r8, [rax+10h]
0x140019881  mov     rcx, [rcx+18h]; unsigned __int16 *
0x140019885  call    DafMakeAepId
0x14001988a  mov     ebx, eax
0x14001988c  test    eax, eax
0x14001988e  js      short loc_14001990F
0x140019890  lea     rcx, [rsi+30h]; lpCriticalSection
0x140019894  call    cs:__imp_EnterCriticalSection
0x14001989a  mov     rdi, [rsp+88h+arg_8]
0x1400198a2  cmp     dword ptr [rsi+20h], 0
0x1400198a6  jnz     short loc_1400198AF
0x1400198a8  mov     ebx, 80640013h
0x1400198ad  jmp     short loc_140019903
0x1400198af  lea     rdx, [rsp+88h+var_48]; void **
0x1400198b4  mov     rcx, rsi; this
0x1400198b7  call    ?GetDasRpcBinding@CAepStoreAccess@@IEAAJPEAPEAX@Z; CAepStoreAccess::GetDasRpcBinding(void * *)
0x1400198bc  mov     ebx, eax
0x1400198be  test    eax, eax
0x1400198c0  js      short loc_140019903
0x1400198c2  lea     rax, dword_14002438C
0x1400198c9  cmp     qword ptr [rsi+10h], 0
0x1400198ce  cmovnz  rax, [rsi+10h]
0x1400198d3  mov     [rsp+88h+var_50], r14
0x1400198d8  mov     [rsp+88h+var_58], r15d
0x1400198dd  mov     [rsp+88h+var_60], rax
0x1400198e2  mov     [rsp+88h+var_68], rdi
0x1400198e7  mov     r9, [rsp+88h+var_48]
0x1400198ec  xor     r8d, r8d; pReturnValue
0x1400198ef  lea     edx, [r8+2]; nProcNum
0x1400198f3  lea     rcx, ?AepStoreAccess_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1400198fa  call    cs:__imp_NdrClientCall3
0x140019900  mov     rbx, rax
0x140019903  lea     rcx, [rsi+30h]; lpCriticalSection
0x140019907  call    cs:__imp_LeaveCriticalSection
0x14001990d  jmp     short loc_14001991E
0x14001990f  mov     rdi, [rsp+88h+arg_8]
0x140019917  jmp     short loc_14001991E
0x140019919  mov     ebx, 80070057h
0x14001991e  test    rdi, rdi
0x140019921  jz      short loc_14001992B
0x140019923  mov     rcx, rdi; void *
0x140019926  call    MIDL_user_free
0x14001992b  mov     eax, ebx
0x14001992d  add     rsp, 58h
0x140019931  pop     r15
0x140019933  pop     r14
0x140019935  pop     rdi
0x140019936  pop     rsi
0x140019937  pop     rbp
0x140019938  pop     rbx
0x140019939  retn
```
