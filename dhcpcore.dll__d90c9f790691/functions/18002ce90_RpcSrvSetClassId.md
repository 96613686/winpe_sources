# RpcSrvSetClassId

- ea: `0x18002ce90`
- end: `0x18002d117`
- name: `RpcSrvSetClassId`
- size: `647`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x180002498`
- `0x180002534`
- `0x18000a654`
- `0x18000eb7c`
- `0x18001ee9c`
- `0x1800251a4`
- `0x18002ce90`
- `0x18002d120`
- `0x180040eb4`
- `0x180041224`
- `0x180047e30`
- `0x18004a868`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d062`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d062`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002cf63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002cf63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002cf92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002cf92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d00f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d00f`

## pseudocode

```c
__int64 __fastcall RpcSrvSetClassId(_WORD *a1, LPVOID *a2, __int64 a3)
{
  LPVOID *p_Ptr; // rbx
  int v8; // r13d
  CRpcWatchDog *v9; // rcx
  unsigned int v10; // esi
  int v11; // r8d
  unsigned int v12; // edi
  const void *v13; // r14
  unsigned int v14; // eax
  int v15; // r12d
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int128 v20; // [rsp+30h] [rbp-38h] BYREF
  _OWORD v21[2]; // [rsp+40h] [rbp-28h] BYREF
  RTL_SRWLOCK *v22; // [rsp+C8h] [rbp+60h] BYREF

  p_Ptr = 0;
  v22 = 0;
  memset(v21, 0, sizeof(v21));
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvSetClassId_New(a1, (__int64)a2, a3);
  v8 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 130, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  v10 = RpcValidateRequests(a1);
  if ( v10 )
    goto LABEL_32;
  *(_QWORD *)&v21[0] = RpcSrvSetClassId;
  CRpcWatchDog::AddEntry(v9, (struct _WatchDogEntry *)v21, v11);
  v8 = 1;
  if ( !a3 || (v12 = *(_DWORD *)(a3 + 16)) == 0 || (v13 = *(const void **)(a3 + 8)) == 0 )
  {
    v12 = 0;
    v13 = 0;
  }
  v14 = DhcpFindAndRefContext(a2, (LPVOID **)&v22);
  p_Ptr = &v22->Ptr;
  v10 = v14;
  if ( v14 )
    goto LABEL_32;
  v15 = 0;
  AcquireSRWLockShared(v22 + 84);
  if ( *((_DWORD *)p_Ptr + 186) == v12 )
  {
    LOBYTE(v15) = v12 == 0;
    if ( !memcmp_0(p_Ptr[92], v13, v12) )
      v15 = 1;
  }
  ReleaseSRWLockShared((PSRWLOCK)p_Ptr + 84);
  if ( v15 )
    goto LABEL_34;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    v20 = (unsigned __int64)v13;
    if ( v13 )
    {
      WORD4(v20) = -1;
      if ( v12 <= 0xFFFF )
        WORD4(v20) = v12;
    }
    else
    {
      WORD4(v20) = 0;
    }
    WPP_SF_Jd_HEX_((_DWORD)v9, 131, v16, (unsigned int)p_Ptr[3], v12, (__int64)&v20);
  }
  v10 = LockDhcpContext((__int64)p_Ptr, 1);
  if ( v10 )
  {
LABEL_32:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 133, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v10);
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)p_Ptr + 84);
    v18 = (__int64)p_Ptr[92];
    if ( v18 )
    {
      DhcpDelClass(v17, v18, *((_DWORD *)p_Ptr + 186));
      p_Ptr[92] = 0;
      *((_DWORD *)p_Ptr + 186) = 0;
    }
    if ( v12 )
    {
      v19 = DhcpAddClass(v17, v13, v12);
      p_Ptr[92] = (LPVOID)v19;
      if ( v19 )
        *((_DWORD *)p_Ptr + 186) = v12;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)p_Ptr + 84);
    if ( *((_DWORD *)p_Ptr + 198) )
    {
      if ( *((_DWORD *)p_Ptr + 495) )
        DhcpCancelDAD(p_Ptr);
      ScheduleWakeUp(p_Ptr, 0);
    }
    UnlockDhcpContext(p_Ptr);
  }
LABEL_34:
  if ( p_Ptr )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_q(1028, 132, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, p_Ptr[3]);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)p_Ptr + 4, 0xFFFFFFFF) == 1 )
      DhcpDestroyContextEx((__int64)p_Ptr);
  }
  if ( v8 )
    CRpcWatchDog::RemoveEntry(v9, (struct _WatchDogEntry *)v21);
  return v10;
}

```

## disassembly

```asm
0x18002ce90  push    rbp
0x18002ce92  push    rbx
0x18002ce93  push    rsi
0x18002ce94  push    rdi
0x18002ce95  push    r12
0x18002ce97  push    r13
0x18002ce99  push    r14
0x18002ce9b  push    r15
0x18002ce9d  mov     rbp, rsp
0x18002cea0  sub     rsp, 68h
0x18002cea4  xor     ebx, ebx
0x18002cea6  xorps   xmm0, xmm0
0x18002cea9  cmp     cs:g_fVelocityApistubStyleUpdate, ebx
0x18002ceaf  mov     r14, r8
0x18002ceb2  mov     r15, rdx
0x18002ceb5  mov     [rbp+arg_18], rbx
0x18002ceb9  mov     rdi, rcx
0x18002cebc  movups  [rbp+var_28], xmm0
0x18002cec0  movups  [rbp+var_18], xmm0
0x18002cec4  jz      short loc_18002CED0
0x18002cec6  call    RpcSrvSetClassId_New
0x18002cecb  jmp     loc_18002D106
0x18002ced0  xor     r13d, r13d
0x18002ced3  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002ceda  jz      short loc_18002CEF2
0x18002cedc  mov     edx, 82h
0x18002cee1  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002cee8  mov     ecx, 404h
0x18002ceed  call    WPP_SF_
0x18002cef2  mov     edx, 4
0x18002cef7  mov     rcx, rdi
0x18002cefa  call    RpcValidateRequests
0x18002ceff  mov     esi, eax
0x18002cf01  test    eax, eax
0x18002cf03  jnz     loc_18002D097
0x18002cf09  lea     rax, RpcSrvSetClassId
0x18002cf10  lea     rdx, [rbp+var_28]; struct _WatchDogEntry *
0x18002cf14  mov     qword ptr [rbp+var_28], rax
0x18002cf18  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002cf1d  lea     r13d, [rsi+1]
0x18002cf21  test    r14, r14
0x18002cf24  jz      short loc_18002CF37
0x18002cf26  mov     edi, [r14+10h]
0x18002cf2a  test    edi, edi
0x18002cf2c  jz      short loc_18002CF37
0x18002cf2e  mov     r14, [r14+8]
0x18002cf32  test    r14, r14
0x18002cf35  jnz     short loc_18002CF3C
0x18002cf37  xor     edi, edi
0x18002cf39  xor     r14d, r14d
0x18002cf3c  lea     rdx, [rbp+arg_18]
0x18002cf40  mov     rcx, r15
0x18002cf43  call    DhcpFindAndRefContext
0x18002cf48  mov     rbx, [rbp+arg_18]
0x18002cf4c  mov     esi, eax
0x18002cf4e  test    eax, eax
0x18002cf50  jnz     loc_18002D097
0x18002cf56  lea     r15, [rbx+2A0h]
0x18002cf5d  xor     r12d, r12d
0x18002cf60  mov     rcx, r15; SRWLock
0x18002cf63  call    cs:__imp_AcquireSRWLockShared
0x18002cf69  cmp     [rbx+2E8h], edi
0x18002cf6f  jnz     short loc_18002CF8F
0x18002cf71  mov     rcx, [rbx+2E0h]; Buf1
0x18002cf78  test    edi, edi
0x18002cf7a  mov     r8d, edi; Size
0x18002cf7d  mov     rdx, r14; Buf2
0x18002cf80  setz    r12b
0x18002cf84  call    memcmp_0
0x18002cf89  test    eax, eax
0x18002cf8b  cmovz   r12d, r13d
0x18002cf8f  mov     rcx, r15; SRWLock
0x18002cf92  call    cs:__imp_ReleaseSRWLockShared
0x18002cf98  test    r12d, r12d
0x18002cf9b  jnz     loc_18002D0B9
0x18002cfa1  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002cfa8  jz      short loc_18002CFF7
0x18002cfaa  xorps   xmm0, xmm0
0x18002cfad  movups  [rbp+var_38], xmm0
0x18002cfb1  mov     qword ptr [rbp+var_38], r14
0x18002cfb5  test    r14, r14
0x18002cfb8  jnz     short loc_18002CFC2
0x18002cfba  xor     eax, eax
0x18002cfbc  mov     word ptr [rbp+var_38+8], ax
0x18002cfc0  jmp     short loc_18002CFD3
0x18002cfc2  mov     eax, 0FFFFh
0x18002cfc7  mov     word ptr [rbp+var_38+8], ax
0x18002cfcb  cmp     edi, eax
0x18002cfcd  ja      short loc_18002CFD3
0x18002cfcf  mov     word ptr [rbp+var_38+8], di
0x18002cfd3  movaps  xmm0, [rbp+var_38]
0x18002cfd7  lea     rax, [rbp+var_38]
0x18002cfdb  movdqa  [rbp+var_38], xmm0
0x18002cfe0  mov     edx, 83h
0x18002cfe5  mov     r9, [rbx+18h]
0x18002cfe9  mov     [rsp+68h+var_40], rax
0x18002cfee  mov     [rsp+68h+var_48], edi
0x18002cff2  call    WPP_SF_Jd_HEX_
0x18002cff7  mov     edx, r13d
0x18002cffa  mov     rcx, rbx
0x18002cffd  call    LockDhcpContext
0x18002d002  mov     esi, eax
0x18002d004  test    eax, eax
0x18002d006  jnz     loc_18002D097
0x18002d00c  mov     rcx, r15; SRWLock
0x18002d00f  call    cs:__imp_AcquireSRWLockExclusive
0x18002d015  mov     rdx, [rbx+2E0h]
0x18002d01c  test    rdx, rdx
0x18002d01f  jz      short loc_18002D03E
0x18002d021  mov     r8d, [rbx+2E8h]
0x18002d028  call    DhcpDelClass
0x18002d02d  mov     qword ptr [rbx+2E0h], 0
0x18002d038  mov     [rbx+2E8h], esi
0x18002d03e  test    edi, edi
0x18002d040  jz      short loc_18002D05F
0x18002d042  mov     r8d, edi
0x18002d045  mov     rdx, r14
0x18002d048  call    DhcpAddClass
0x18002d04d  mov     [rbx+2E0h], rax
0x18002d054  test    rax, rax
0x18002d057  jz      short loc_18002D05F
0x18002d059  mov     [rbx+2E8h], edi
0x18002d05f  mov     rcx, r15; SRWLock
0x18002d062  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d068  mov     eax, [rbx+318h]
0x18002d06e  test    eax, eax
0x18002d070  jz      short loc_18002D08D
0x18002d072  cmp     dword ptr [rbx+7BCh], 0
0x18002d079  jz      short loc_18002D083
0x18002d07b  mov     rcx, rbx
0x18002d07e  call    DhcpCancelDAD
0x18002d083  xor     edx, edx
0x18002d085  mov     rcx, rbx
0x18002d088  call    ScheduleWakeUp
0x18002d08d  mov     rcx, rbx
0x18002d090  call    UnlockDhcpContext
0x18002d095  jmp     short loc_18002D0B9
0x18002d097  test    byte ptr cs:xmmword_1800616A0, 2
0x18002d09e  jz      short loc_18002D0B9
0x18002d0a0  mov     edx, 85h
0x18002d0a5  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002d0ac  mov     ecx, 401h
0x18002d0b1  mov     r9d, esi
0x18002d0b4  call    WPP_SF_D
0x18002d0b9  test    rbx, rbx
0x18002d0bc  jz      short loc_18002D0F6
0x18002d0be  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002d0c5  jz      short loc_18002D0E1
0x18002d0c7  mov     r9, [rbx+18h]
0x18002d0cb  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002d0d2  mov     edx, 84h
0x18002d0d7  mov     ecx, 404h
0x18002d0dc  call    WPP_SF_q
0x18002d0e1  or      eax, 0FFFFFFFFh
0x18002d0e4  lock xadd [rbx+10h], eax
0x18002d0e9  cmp     eax, 1
0x18002d0ec  jnz     short loc_18002D0F6
0x18002d0ee  mov     rcx, rbx
0x18002d0f1  call    DhcpDestroyContextEx
0x18002d0f6  test    r13d, r13d
0x18002d0f9  jz      short loc_18002D104
0x18002d0fb  lea     rdx, [rbp+var_28]; struct _WatchDogEntry *
0x18002d0ff  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002d104  mov     eax, esi
0x18002d106  add     rsp, 68h
0x18002d10a  pop     r15
0x18002d10c  pop     r14
0x18002d10e  pop     r13
0x18002d110  pop     r12
0x18002d112  pop     rdi
0x18002d113  pop     rsi
0x18002d114  pop     rbx
0x18002d115  pop     rbp
0x18002d116  retn
```
