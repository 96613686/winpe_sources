# RpcSrvGetClassId_New

- ea: `0x180028724`
- end: `0x180028882`
- name: `RpcSrvGetClassId_New`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180028590`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x180002534`
- `0x18000eb7c`
- `0x180028724`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800287f3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800287f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800287de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800287de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002882b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002882b`

## pseudocode

```c
__int64 __fastcall RpcSrvGetClassId_New(_WORD *a1, LPVOID *a2, __int64 a3)
{
  CRpcWatchDog *v6; // rcx
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned int v9; // eax
  CRpcWatchDog *v10; // rcx
  LPVOID *p_Ptr; // rdi
  unsigned int v12; // eax
  HLOCAL v13; // rax
  _QWORD v15[9]; // [rsp+20h] [rbp-48h] BYREF
  RTL_SRWLOCK *v16; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  memset(v15, 0, 32);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 134, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, a2);
  v7 = RpcValidateRequests(a1);
  if ( !v7 )
  {
    if ( !a3 || *(_DWORD *)(a3 + 16) || *(_QWORD *)(a3 + 8) )
    {
      v7 = 87;
    }
    else
    {
      v15[0] = RpcSrvGetClassId;
      CRpcWatchDog::AddEntry(v6, (struct _WatchDogEntry *)v15, v8);
      v9 = DhcpFindAndRefContext(a2, (LPVOID **)&v16);
      p_Ptr = &v16->Ptr;
      v7 = v9;
      if ( !v9 )
      {
        AcquireSRWLockShared(v16 + 84);
        v12 = *((_DWORD *)p_Ptr + 186);
        if ( v12 )
        {
          v13 = LocalAlloc(0x40u, v12);
          *(_QWORD *)(a3 + 8) = v13;
          if ( v13 )
          {
            v7 = 0;
            memcpy_0(v13, p_Ptr[92], *((unsigned int *)p_Ptr + 186));
            *(_DWORD *)(a3 + 16) = *((_DWORD *)p_Ptr + 186);
          }
          else
          {
            v7 = 8;
          }
        }
        ReleaseSRWLockShared((PSRWLOCK)p_Ptr + 84);
      }
      if ( p_Ptr && _InterlockedExchangeAdd((volatile signed __int32 *)p_Ptr + 4, 0xFFFFFFFF) == 1 )
        DhcpDestroyContextEx((__int64)p_Ptr);
      CRpcWatchDog::RemoveEntry(v10, (struct _WatchDogEntry *)v15);
    }
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 135, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180028724  mov     rax, rsp
0x180028727  push    rbx
0x180028728  push    rbp
0x180028729  push    rsi
0x18002872a  push    rdi
0x18002872b  sub     rsp, 48h
0x18002872f  xorps   xmm0, xmm0
0x180028732  mov     qword ptr [rax+20h], 0
0x18002873a  movups  xmmword ptr [rax-48h], xmm0
0x18002873e  mov     rsi, r8
0x180028741  mov     rdi, rdx
0x180028744  movups  xmmword ptr [rax-38h], xmm0
0x180028748  mov     rbx, rcx
0x18002874b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180028752  jz      short loc_18002876D
0x180028754  mov     edx, 86h
0x180028759  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180028760  mov     ecx, 404h
0x180028765  mov     r9, rdi
0x180028768  call    WPP_SF_q
0x18002876d  mov     edx, 1
0x180028772  mov     rcx, rbx
0x180028775  call    RpcValidateRequests
0x18002877a  mov     ebx, eax
0x18002877c  test    eax, eax
0x18002877e  jnz     loc_180028855
0x180028784  test    rsi, rsi
0x180028787  jnz     short loc_180028793
0x180028789  mov     ebx, 57h ; 'W'
0x18002878e  jmp     loc_180028855
0x180028793  cmp     dword ptr [rsi+10h], 0
0x180028797  jnz     short loc_180028789
0x180028799  cmp     qword ptr [rsi+8], 0
0x18002879e  jnz     short loc_180028789
0x1800287a0  lea     rax, RpcSrvGetClassId
0x1800287a7  lea     rdx, [rsp+68h+var_48]; struct _WatchDogEntry *
0x1800287ac  mov     [rsp+68h+var_48], rax
0x1800287b1  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x1800287b6  lea     rdx, [rsp+68h+arg_18]
0x1800287be  mov     rcx, rdi
0x1800287c1  call    DhcpFindAndRefContext
0x1800287c6  mov     rdi, [rsp+68h+arg_18]
0x1800287ce  mov     ebx, eax
0x1800287d0  test    eax, eax
0x1800287d2  jnz     short loc_180028831
0x1800287d4  lea     rbp, [rdi+2A0h]
0x1800287db  mov     rcx, rbp; SRWLock
0x1800287de  call    cs:__imp_AcquireSRWLockShared
0x1800287e4  mov     eax, [rdi+2E8h]
0x1800287ea  test    eax, eax
0x1800287ec  jz      short loc_180028828
0x1800287ee  mov     edx, eax; uBytes
0x1800287f0  lea     ecx, [rbx+40h]; uFlags
0x1800287f3  call    cs:__imp_LocalAlloc
0x1800287f9  mov     [rsi+8], rax
0x1800287fd  test    rax, rax
0x180028800  jnz     short loc_180028807
0x180028802  lea     ebx, [rax+8]
0x180028805  jmp     short loc_180028828
0x180028807  mov     r8d, [rdi+2E8h]; Size
0x18002880e  xor     ebx, ebx
0x180028810  mov     rdx, [rdi+2E0h]; Src
0x180028817  mov     rcx, rax; void *
0x18002881a  call    memcpy_0
0x18002881f  mov     eax, [rdi+2E8h]
0x180028825  mov     [rsi+10h], eax
0x180028828  mov     rcx, rbp; SRWLock
0x18002882b  call    cs:__imp_ReleaseSRWLockShared
0x180028831  test    rdi, rdi
0x180028834  jz      short loc_18002884B
0x180028836  or      eax, 0FFFFFFFFh
0x180028839  lock xadd [rdi+10h], eax
0x18002883e  cmp     eax, 1
0x180028841  jnz     short loc_18002884B
0x180028843  mov     rcx, rdi
0x180028846  call    DhcpDestroyContextEx
0x18002884b  lea     rdx, [rsp+68h+var_48]; struct _WatchDogEntry *
0x180028850  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180028855  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002885c  jz      short loc_180028877
0x18002885e  mov     edx, 87h
0x180028863  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002886a  mov     ecx, 404h
0x18002886f  mov     r9d, ebx
0x180028872  call    WPP_SF_D
0x180028877  mov     eax, ebx
0x180028879  add     rsp, 48h
0x18002887d  pop     rdi
0x18002887e  pop     rsi
0x18002887f  pop     rbp
0x180028880  pop     rbx
0x180028881  retn
```
