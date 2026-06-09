# wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x140012014`
- end: `0x1400120ae`
- name: `?LockExclusive@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400119c0`
- `0x1400123e0`
- `0x140012754`
- `0x1400128fc`
- `0x140012ae0`

## callees

- `0x140012014`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012044`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012044`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001207f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012095`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001207f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012095`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  PSRWLOCK *p_SRWLock; // rax
  char v6; // di
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK v9; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(SRWLock) = 0;
  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    p_SRWLock = &v9;
    v6 = 1;
  }
  else
  {
    p_SRWLock = &SRWLock;
    v6 = 2;
    v4 = 0;
  }
  *a2 = v4;
  *p_SRWLock = 0;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  if ( (v6 & 1) != 0 && v9 )
    ReleaseSRWLockExclusive(v9);
  return a2;
}

```

## disassembly

```asm
0x140012014  mov     [rsp+arg_10], rbx
0x140012019  mov     [rsp+arg_18], rsi
0x14001201e  push    rdi
0x14001201f  sub     rsp, 20h
0x140012023  mov     dword ptr [rsp+28h+SRWLock], 0
0x14001202b  mov     rsi, rdx
0x14001202e  mov     rbx, [rcx+118h]
0x140012035  test    rbx, rbx
0x140012038  jz      short loc_140012056
0x14001203a  add     rbx, 108h
0x140012041  mov     rcx, rbx; SRWLock
0x140012044  call    cs:__imp_AcquireSRWLockExclusive
0x14001204a  lea     rax, [rsp+28h+arg_8]
0x14001204f  mov     edi, 1
0x140012054  jmp     short loc_140012062
0x140012056  lea     rax, [rsp+28h+SRWLock]
0x14001205b  mov     edi, 2
0x140012060  xor     ebx, ebx
0x140012062  mov     [rsi], rbx
0x140012065  mov     qword ptr [rax], 0
0x14001206c  test    dil, 2
0x140012070  jz      short loc_140012085
0x140012072  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x140012077  and     edi, 0FFFFFFFDh
0x14001207a  test    rcx, rcx
0x14001207d  jz      short loc_140012085
0x14001207f  call    cs:__imp_ReleaseSRWLockExclusive
0x140012085  test    dil, 1
0x140012089  jz      short loc_14001209B
0x14001208b  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x140012090  test    rcx, rcx
0x140012093  jz      short loc_14001209B
0x140012095  call    cs:__imp_ReleaseSRWLockExclusive
0x14001209b  mov     rbx, [rsp+28h+arg_10]
0x1400120a0  mov     rax, rsi
0x1400120a3  mov     rsi, [rsp+28h+arg_18]
0x1400120a8  add     rsp, 20h
0x1400120ac  pop     rdi
0x1400120ad  retn
```
