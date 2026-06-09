# CAepStoreAccess::Create(ushort const *,ulong,_DEVPROPERTY * const)

- ea: `0x140019330`
- end: `0x140019402`
- name: `?Create@CAepStoreAccess@@UEAAJPEBGKQEAU_DEVPROPERTY@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(CAepStoreAccess *this, unsigned __int16 *, int, struct _DEVPROPERTY *const)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140009090`
- `0x140019330`
- `0x1400194f4`
- `0x140019940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400193e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400193e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019377`
- `RPCRT4!NdrClientCall3` at `0x1400193d3`
- `RPCRT4!NdrClientCall3` at `0x1400193d3`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::Create(
        CAepStoreAccess *this,
        unsigned __int16 *a2,
        int a3,
        struct _DEVPROPERTY *const a4)
{
  int AepId; // ebx
  int *v8; // rax
  int v10; // [rsp+30h] [rbp-58h]
  void *v11; // [rsp+40h] [rbp-48h] BYREF

  v11 = 0;
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
                                0,
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
  return (unsigned int)AepId;
}

```

## disassembly

```asm
0x140019330  mov     rax, rsp
0x140019333  push    rbx
0x140019334  push    rbp
0x140019335  push    rsi
0x140019336  push    rdi
0x140019337  push    r14
0x140019339  push    r15
0x14001933b  sub     rsp, 58h
0x14001933f  mov     r14, r9
0x140019342  mov     r15d, r8d
0x140019345  mov     rdi, rcx
0x140019348  mov     qword ptr [rax+8], 0
0x140019350  mov     qword ptr [rax-48h], 0
0x140019358  lea     r8, [rax+8]
0x14001935c  mov     rcx, [rcx+18h]; unsigned __int16 *
0x140019360  call    DafMakeAepId
0x140019365  mov     ebx, eax
0x140019367  mov     rsi, [rsp+88h+arg_0]
0x14001936f  test    eax, eax
0x140019371  js      short loc_1400193E6
0x140019373  lea     rcx, [rdi+30h]; lpCriticalSection
0x140019377  call    cs:__imp_EnterCriticalSection
0x14001937d  cmp     dword ptr [rdi+20h], 0
0x140019381  jnz     short loc_14001938A
0x140019383  mov     ebx, 80640013h
0x140019388  jmp     short loc_1400193DC
0x14001938a  lea     rdx, [rsp+88h+var_48]; void **
0x14001938f  mov     rcx, rdi; this
0x140019392  call    ?GetDasRpcBinding@CAepStoreAccess@@IEAAJPEAPEAX@Z; CAepStoreAccess::GetDasRpcBinding(void * *)
0x140019397  mov     ebx, eax
0x140019399  test    eax, eax
0x14001939b  js      short loc_1400193DC
0x14001939d  lea     rax, dword_14002438C
0x1400193a4  cmp     qword ptr [rdi+10h], 0
0x1400193a9  cmovnz  rax, [rdi+10h]
0x1400193ae  mov     [rsp+88h+var_50], r14
0x1400193b3  mov     [rsp+88h+var_58], r15d
0x1400193b8  mov     [rsp+88h+var_60], rax
0x1400193bd  mov     [rsp+88h+var_68], rsi
0x1400193c2  mov     r9, [rsp+88h+var_48]
0x1400193c7  xor     r8d, r8d; pReturnValue
0x1400193ca  xor     edx, edx; nProcNum
0x1400193cc  lea     rcx, ?AepStoreAccess_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1400193d3  call    cs:__imp_NdrClientCall3
0x1400193d9  mov     rbx, rax
0x1400193dc  lea     rcx, [rdi+30h]; lpCriticalSection
0x1400193e0  call    cs:__imp_LeaveCriticalSection
0x1400193e6  test    rsi, rsi
0x1400193e9  jz      short loc_1400193F3
0x1400193eb  mov     rcx, rsi; void *
0x1400193ee  call    MIDL_user_free
0x1400193f3  mov     eax, ebx
0x1400193f5  add     rsp, 58h
0x1400193f9  pop     r15
0x1400193fb  pop     r14
0x1400193fd  pop     rdi
0x1400193fe  pop     rsi
0x1400193ff  pop     rbp
0x140019400  pop     rbx
0x140019401  retn
```
