# CAepStoreAccess::Delete(ushort const *)

- ea: `0x140019410`
- end: `0x1400194d0`
- name: `?Delete@CAepStoreAccess@@UEAAJPEBG@Z`
- size: `192`
- prototype: `__int64 __fastcall(CAepStoreAccess *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140009090`
- `0x140019410`
- `0x1400194f4`
- `0x140019940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400194ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400194ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001944d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001944d`
- `RPCRT4!NdrClientCall3` at `0x1400194a1`
- `RPCRT4!NdrClientCall3` at `0x1400194a1`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::Delete(CAepStoreAccess *this, unsigned __int16 *a2)
{
  int AepId; // ebx
  int *v4; // rax
  void *v6; // [rsp+60h] [rbp+18h] BYREF

  v6 = 0;
  AepId = DafMakeAepId(*((unsigned __int16 **)this + 3), a2);
  if ( AepId >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( *((_DWORD *)this + 8) )
    {
      AepId = CAepStoreAccess::GetDasRpcBinding(this, &v6);
      if ( AepId >= 0 )
      {
        v4 = &dword_14002438C;
        if ( *((_QWORD *)this + 2) )
          v4 = (int *)*((_QWORD *)this + 2);
        AepId = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&AepStoreAccess_ProxyInfo, 1u, 0, v6, 0, v4).Pointer;
      }
    }
    else
    {
      AepId = -2140930029;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  }
  return (unsigned int)AepId;
}

```

## disassembly

```asm
0x140019410  mov     rax, rsp
0x140019413  mov     [rax+10h], rbx
0x140019417  push    rbp
0x140019418  push    rsi
0x140019419  push    rdi
0x14001941a  sub     rsp, 30h
0x14001941e  mov     rdi, rcx
0x140019421  mov     qword ptr [rax+8], 0
0x140019429  mov     qword ptr [rax+18h], 0
0x140019431  lea     r8, [rax+8]
0x140019435  mov     rcx, [rcx+18h]; unsigned __int16 *
0x140019439  call    DafMakeAepId
0x14001943e  mov     ebx, eax
0x140019440  mov     rsi, [rsp+48h+arg_0]
0x140019445  test    eax, eax
0x140019447  js      short loc_1400194B4
0x140019449  lea     rcx, [rdi+30h]; lpCriticalSection
0x14001944d  call    cs:__imp_EnterCriticalSection
0x140019453  cmp     dword ptr [rdi+20h], 0
0x140019457  jnz     short loc_140019460
0x140019459  mov     ebx, 80640013h
0x14001945e  jmp     short loc_1400194AA
0x140019460  lea     rdx, [rsp+48h+arg_10]; void **
0x140019465  mov     rcx, rdi; this
0x140019468  call    ?GetDasRpcBinding@CAepStoreAccess@@IEAAJPEAPEAX@Z; CAepStoreAccess::GetDasRpcBinding(void * *)
0x14001946d  mov     ebx, eax
0x14001946f  test    eax, eax
0x140019471  js      short loc_1400194AA
0x140019473  lea     rax, dword_14002438C
0x14001947a  cmp     qword ptr [rdi+10h], 0
0x14001947f  cmovnz  rax, [rdi+10h]
0x140019484  mov     [rsp+48h+var_20], rax
0x140019489  mov     [rsp+48h+var_28], rsi
0x14001948e  mov     r9, [rsp+48h+arg_10]
0x140019493  xor     r8d, r8d; pReturnValue
0x140019496  lea     edx, [r8+1]; nProcNum
0x14001949a  lea     rcx, ?AepStoreAccess_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1400194a1  call    cs:__imp_NdrClientCall3
0x1400194a7  mov     rbx, rax
0x1400194aa  lea     rcx, [rdi+30h]; lpCriticalSection
0x1400194ae  call    cs:__imp_LeaveCriticalSection
0x1400194b4  test    rsi, rsi
0x1400194b7  jz      short loc_1400194C1
0x1400194b9  mov     rcx, rsi; void *
0x1400194bc  call    MIDL_user_free
0x1400194c1  mov     eax, ebx
0x1400194c3  mov     rbx, [rsp+48h+arg_8]
0x1400194c8  add     rsp, 30h
0x1400194cc  pop     rdi
0x1400194cd  pop     rsi
0x1400194ce  pop     rbp
0x1400194cf  retn
```
