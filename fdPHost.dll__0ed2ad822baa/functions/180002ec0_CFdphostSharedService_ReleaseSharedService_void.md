# CFdphostSharedService::ReleaseSharedService(void)

- ea: `0x180002ec0`
- end: `0x180002f7d`
- name: `?ReleaseSharedService@CFdphostSharedService@@UEAAKXZ`
- size: `189`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000284c`
- `0x180002ec0`
- `0x180002f84`
- `0x180002fd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002f41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002f41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002efd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002efd`
- `combase!__imp_CoReleaseSharedService` at `0x180002f10`
- `combase!__imp_CoReleaseSharedService` at `0x180002f10`

## pseudocode

```c
__int64 __fastcall CFdphostSharedService::ReleaseSharedService(RTL_SRWLOCK *this)
{
  bool v2; // zf
  unsigned int Ptr_high; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
  AcquireSRWLockExclusive(this + 2);
  v2 = HIDWORD(this[1].Ptr)-- == 1;
  Ptr_high = HIDWORD(this[1].Ptr);
  if ( v2 )
  {
    CoReleaseSharedService(LODWORD(this[3].Ptr));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a6e3756ed29831dc62ead4dd4235b941_Traceguids);
  }
  ReleaseSRWLockExclusive(this + 2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sqP(*((_QWORD *)WPP_GLOBAL_Control + 2), 23);
  return Ptr_high;
}

```

## disassembly

```asm
0x180002ec0  push    rbx
0x180002ec2  push    rsi
0x180002ec3  push    rdi
0x180002ec4  push    r14
0x180002ec6  sub     rsp, 38h
0x180002eca  mov     rbx, rcx
0x180002ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ed4  lea     r14, WPP_GLOBAL_Control
0x180002edb  cmp     rcx, r14
0x180002ede  jz      short loc_180002EF9
0x180002ee0  cmp     byte ptr [rcx+19h], 4
0x180002ee4  jb      short loc_180002EF9
0x180002ee6  mov     rcx, [rcx+10h]
0x180002eea  mov     edx, 15h
0x180002eef  mov     [rsp+58h+var_38], rbx
0x180002ef4  call    WPP_SF_sq
0x180002ef9  lea     rcx, [rbx+10h]; SRWLock
0x180002efd  call    cs:__imp_AcquireSRWLockExclusive
0x180002f03  sub     dword ptr [rbx+0Ch], 1
0x180002f07  movsxd  rdi, dword ptr [rbx+0Ch]
0x180002f0b  jnz     short loc_180002F3D
0x180002f0d  mov     ecx, [rbx+18h]
0x180002f10  call    cs:__imp_CoReleaseSharedService
0x180002f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f1d  cmp     rcx, r14
0x180002f20  jz      short loc_180002F3D
0x180002f22  cmp     byte ptr [rcx+19h], 4
0x180002f26  jb      short loc_180002F3D
0x180002f28  mov     rcx, [rcx+10h]
0x180002f2c  lea     r8, WPP_a6e3756ed29831dc62ead4dd4235b941_Traceguids
0x180002f33  mov     edx, 16h
0x180002f38  call    WPP_SF_s
0x180002f3d  lea     rcx, [rbx+10h]; SRWLock
0x180002f41  call    cs:__imp_ReleaseSRWLockExclusive
0x180002f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f4e  cmp     rcx, r14
0x180002f51  jz      short loc_180002F71
0x180002f53  cmp     byte ptr [rcx+19h], 4
0x180002f57  jb      short loc_180002F71
0x180002f59  mov     rcx, [rcx+10h]
0x180002f5d  mov     edx, 17h
0x180002f62  mov     [rsp+58h+var_30], rdi
0x180002f67  mov     [rsp+58h+var_38], rbx
0x180002f6c  call    WPP_SF_sqP
0x180002f71  mov     eax, edi
0x180002f73  add     rsp, 38h
0x180002f77  pop     r14
0x180002f79  pop     rdi
0x180002f7a  pop     rsi
0x180002f7b  pop     rbx
0x180002f7c  retn
```
