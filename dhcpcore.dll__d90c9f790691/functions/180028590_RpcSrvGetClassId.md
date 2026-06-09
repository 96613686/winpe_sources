# RpcSrvGetClassId

- ea: `0x180028590`
- end: `0x18002871d`
- name: `RpcSrvGetClassId`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x180002534`
- `0x18000eb7c`
- `0x180028590`
- `0x180028724`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180028675`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180028675`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028660`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180028660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800286e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800286e0`

## pseudocode

```c
__int64 __fastcall RpcSrvGetClassId(_WORD *a1, LPVOID *a2, __int64 a3, __int64 a4)
{
  LPVOID *p_Ptr; // rbx
  int v9; // r14d
  int v10; // ebp
  CRpcWatchDog *v11; // rcx
  unsigned int v12; // edi
  int v13; // r8d
  unsigned int v14; // eax
  unsigned int v15; // eax
  HLOCAL v16; // rax
  _QWORD v17[11]; // [rsp+20h] [rbp-58h] BYREF
  RTL_SRWLOCK *v18; // [rsp+98h] [rbp+20h] BYREF

  p_Ptr = 0;
  v18 = 0;
  memset(v17, 0, 32);
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvGetClassId_New(a1, a2, a3, a4);
  v9 = 0;
  v10 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 136, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  v12 = RpcValidateRequests(a1);
  if ( v12 )
  {
LABEL_15:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 137, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v12);
    if ( !v9 )
      goto LABEL_19;
    goto LABEL_18;
  }
  if ( !a3 || *(_DWORD *)(a3 + 16) || *(_QWORD *)(a3 + 8) )
  {
    v12 = 87;
    goto LABEL_15;
  }
  v17[0] = RpcSrvGetClassId;
  CRpcWatchDog::AddEntry(v11, (struct _WatchDogEntry *)v17, v13);
  v10 = 1;
  v14 = DhcpFindAndRefContext(a2, (LPVOID **)&v18);
  p_Ptr = &v18->Ptr;
  v12 = v14;
  if ( v14 )
    goto LABEL_15;
  AcquireSRWLockShared(v18 + 84);
  v15 = *((_DWORD *)p_Ptr + 186);
  if ( v15 )
  {
    v16 = LocalAlloc(0x40u, v15);
    *(_QWORD *)(a3 + 8) = v16;
    if ( !v16 )
    {
      v12 = 8;
      v9 = 1;
      goto LABEL_15;
    }
    memcpy_0(v16, p_Ptr[92], *((unsigned int *)p_Ptr + 186));
    *(_DWORD *)(a3 + 16) = *((_DWORD *)p_Ptr + 186);
  }
LABEL_18:
  ReleaseSRWLockShared((PSRWLOCK)p_Ptr + 84);
LABEL_19:
  if ( p_Ptr && _InterlockedExchangeAdd((volatile signed __int32 *)p_Ptr + 4, 0xFFFFFFFF) == 1 )
    DhcpDestroyContextEx((__int64)p_Ptr);
  if ( v10 )
    CRpcWatchDog::RemoveEntry(v11, (struct _WatchDogEntry *)v17);
  return v12;
}

```

## disassembly

```asm
0x180028590  mov     rax, rsp
0x180028593  push    rbx
0x180028594  push    rbp
0x180028595  push    rsi
0x180028596  push    rdi
0x180028597  push    r14
0x180028599  push    r15
0x18002859b  sub     rsp, 48h
0x18002859f  xor     ebx, ebx
0x1800285a1  xorps   xmm0, xmm0
0x1800285a4  cmp     cs:g_fVelocityApistubStyleUpdate, ebx
0x1800285aa  mov     rsi, r8
0x1800285ad  mov     r15, rdx
0x1800285b0  mov     [rax+20h], rbx
0x1800285b4  mov     rdi, rcx
0x1800285b7  movups  xmmword ptr [rax-58h], xmm0
0x1800285bb  movups  xmmword ptr [rax-48h], xmm0
0x1800285bf  jz      short loc_1800285CB
0x1800285c1  call    RpcSrvGetClassId_New
0x1800285c6  jmp     loc_180028710
0x1800285cb  xor     r14d, r14d
0x1800285ce  xor     ebp, ebp
0x1800285d0  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800285d7  jz      short loc_1800285EF
0x1800285d9  mov     edx, 88h
0x1800285de  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x1800285e5  mov     ecx, 404h
0x1800285ea  call    WPP_SF_
0x1800285ef  mov     edx, 1
0x1800285f4  mov     rcx, rdi
0x1800285f7  call    RpcValidateRequests
0x1800285fc  mov     edi, eax
0x1800285fe  test    eax, eax
0x180028600  jnz     loc_1800286B2
0x180028606  test    rsi, rsi
0x180028609  jz      loc_1800286AD
0x18002860f  cmp     [rsi+10h], ebx
0x180028612  jnz     loc_1800286AD
0x180028618  cmp     [rsi+8], rbx
0x18002861c  jnz     loc_1800286AD
0x180028622  lea     rax, RpcSrvGetClassId
0x180028629  lea     rdx, [rsp+78h+var_58]; struct _WatchDogEntry *
0x18002862e  mov     [rsp+78h+var_58], rax
0x180028633  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180028638  lea     rdx, [rsp+78h+arg_18]
0x180028640  mov     rcx, r15
0x180028643  lea     ebp, [rdi+1]
0x180028646  call    DhcpFindAndRefContext
0x18002864b  mov     rbx, [rsp+78h+arg_18]
0x180028653  mov     edi, eax
0x180028655  test    eax, eax
0x180028657  jnz     short loc_1800286B2
0x180028659  lea     rcx, [rbx+2A0h]; SRWLock
0x180028660  call    cs:__imp_AcquireSRWLockShared
0x180028666  mov     eax, [rbx+2E8h]
0x18002866c  test    eax, eax
0x18002866e  jz      short loc_1800286D9
0x180028670  mov     edx, eax; uBytes
0x180028672  lea     ecx, [rbp+3Fh]; uFlags
0x180028675  call    cs:__imp_LocalAlloc
0x18002867b  mov     [rsi+8], rax
0x18002867f  test    rax, rax
0x180028682  jnz     short loc_18002868C
0x180028684  lea     edi, [rbp+7]
0x180028687  mov     r14d, ebp
0x18002868a  jmp     short loc_1800286B2
0x18002868c  mov     r8d, [rbx+2E8h]; Size
0x180028693  mov     rcx, rax; void *
0x180028696  mov     rdx, [rbx+2E0h]; Src
0x18002869d  call    memcpy_0
0x1800286a2  mov     eax, [rbx+2E8h]
0x1800286a8  mov     [rsi+10h], eax
0x1800286ab  jmp     short loc_1800286D9
0x1800286ad  mov     edi, 57h ; 'W'
0x1800286b2  test    byte ptr cs:xmmword_1800616A0, 2
0x1800286b9  jz      short loc_1800286D4
0x1800286bb  mov     edx, 89h
0x1800286c0  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x1800286c7  mov     ecx, 401h
0x1800286cc  mov     r9d, edi
0x1800286cf  call    WPP_SF_D
0x1800286d4  test    r14d, r14d
0x1800286d7  jz      short loc_1800286E6
0x1800286d9  lea     rcx, [rbx+2A0h]; SRWLock
0x1800286e0  call    cs:__imp_ReleaseSRWLockShared
0x1800286e6  test    rbx, rbx
0x1800286e9  jz      short loc_180028700
0x1800286eb  or      eax, 0FFFFFFFFh
0x1800286ee  lock xadd [rbx+10h], eax
0x1800286f3  cmp     eax, 1
0x1800286f6  jnz     short loc_180028700
0x1800286f8  mov     rcx, rbx
0x1800286fb  call    DhcpDestroyContextEx
0x180028700  test    ebp, ebp
0x180028702  jz      short loc_18002870E
0x180028704  lea     rdx, [rsp+78h+var_58]; struct _WatchDogEntry *
0x180028709  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002870e  mov     eax, edi
0x180028710  add     rsp, 48h
0x180028714  pop     r15
0x180028716  pop     r14
0x180028718  pop     rdi
0x180028719  pop     rsi
0x18002871a  pop     rbp
0x18002871b  pop     rbx
0x18002871c  retn
```
