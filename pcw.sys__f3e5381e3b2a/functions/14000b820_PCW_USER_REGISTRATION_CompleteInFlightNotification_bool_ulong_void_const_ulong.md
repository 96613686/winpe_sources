# PCW_USER_REGISTRATION::CompleteInFlightNotification(bool *,ulong,void const *,ulong)

- ea: `0x14000b820`
- end: `0x14000ba00`
- name: `?CompleteInFlightNotification@PCW_USER_REGISTRATION@@QEAAJPEA_NKPEBXK@Z`
- size: `480`
- prototype: `__int64 __fastcall(PCW_USER_REGISTRATION *this, bool *, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a0e0`

## callees

- `0x140001370`
- `0x14000b76c`
- `0x14000b820`
- `0x14000bf58`
- `0x14000bfd4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b84e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b84e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b92c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b9d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b92c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b9d6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b863`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b863`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b920`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b9ca`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b920`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b9ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b999`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b999`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000b89d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000b89d`

## pseudocode

```c
__int64 __fastcall PCW_USER_REGISTRATION::CompleteInFlightNotification(
        PCW_USER_REGISTRATION *this,
        bool *a2,
        unsigned int a3,
        const void *a4,
        unsigned int a5)
{
  unsigned int CurrentProcessId; // eax
  PCW_NOTIFICATION *v10; // rcx
  unsigned int v11; // eax
  volatile signed __int32 *v12; // r8
  unsigned int v13; // r14d
  char v14; // al
  _QWORD **v16; // rsi
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rdi
  volatile signed __int32 *v20; // [rsp+20h] [rbp-48h] BYREF
  __int128 v21; // [rsp+28h] [rbp-40h] BYREF

  v21 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)this + 32, 0);
  if ( !*((_BYTE *)this + 95) || *((_BYTE *)this + 92) )
  {
    ExReleasePushLockExclusiveEx((char *)this + 32, 0);
    KeLeaveCriticalRegion();
    return 3221225860LL;
  }
  else
  {
    if ( *((_QWORD *)this + 10) )
    {
      DWORD1(v21) = a5;
      LODWORD(v21) = 0;
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v10 = (PCW_NOTIFICATION *)*((_QWORD *)this + 10);
      *((_QWORD *)&v21 + 1) = __PAIR64__(a3, CurrentProcessId);
      v11 = PCW_NOTIFICATION::Complete(v10, (struct PCW_REPLYITEM_BUFFER *)&v21, a4);
      v12 = (volatile signed __int32 *)*((_QWORD *)this + 10);
      v13 = v11;
      *((_QWORD *)this + 10) = 0;
      if ( v12 && _InterlockedExchangeAdd(v12 + 19, 0xFFFFFFFF) == 1 )
        ExFreePoolWithTag((PVOID)v12, 0);
    }
    else
    {
      v13 = 0;
    }
    v14 = *((_BYTE *)this + 93);
    *((_BYTE *)this + 95) = 0;
    *a2 = v14;
    if ( !*((_BYTE *)this + 93) )
    {
      if ( *((_BYTE *)this + 94) )
      {
        *((_BYTE *)this + 94) = 0;
        PCW_USER_REGISTRATION::DeliverGenericDisconnectNotification(this);
      }
      else
      {
        v16 = (_QWORD **)((char *)this + 64);
        while ( 1 )
        {
          v17 = *v16;
          if ( *v16 == v16 )
            break;
          if ( (_QWORD **)v17[1] != v16 || (v18 = (_QWORD *)*v17, *(_QWORD **)(*v17 + 8LL) != v17) )
            __fastfail(3u);
          *v16 = v18;
          v18[1] = v16;
          v19 = v17[2];
          v17[2] = 0;
          if ( v17 )
            ExFreePoolWithTag(v17, 0);
          if ( !*(_BYTE *)(v19 + 68) )
          {
            v20 = (volatile signed __int32 *)v19;
            PCW_USER_REGISTRATION::DeliverNotification((__int64)this, &v20);
            break;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 76), 0xFFFFFFFF) == 1 )
            ExFreePoolWithTag((PVOID)v19, 0);
        }
      }
    }
    ExReleasePushLockExclusiveEx((char *)this + 32, 0);
    KeLeaveCriticalRegion();
    return v13;
  }
}

```

## disassembly

```asm
0x14000b820  push    rbx
0x14000b822  push    rbp
0x14000b823  push    rsi
0x14000b824  push    rdi
0x14000b825  push    r14
0x14000b827  sub     rsp, 40h
0x14000b82b  mov     rax, cs:__security_cookie
0x14000b832  xor     rax, rsp
0x14000b835  mov     [rsp+68h+var_30], rax
0x14000b83a  xorps   xmm0, xmm0
0x14000b83d  mov     r14, r9
0x14000b840  movups  [rsp+68h+var_40], xmm0
0x14000b845  mov     esi, r8d
0x14000b848  mov     rdi, rdx
0x14000b84b  mov     rbx, rcx
0x14000b84e  call    cs:__imp_KeEnterCriticalRegion
0x14000b855  nop     dword ptr [rax+rax+00h]
0x14000b85a  lea     rbp, [rbx+20h]
0x14000b85e  xor     edx, edx
0x14000b860  mov     rcx, rbp
0x14000b863  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b86a  nop     dword ptr [rax+rax+00h]
0x14000b86f  cmp     byte ptr [rbx+5Fh], 0
0x14000b873  jz      loc_14000B9C5
0x14000b879  cmp     byte ptr [rbx+5Ch], 0
0x14000b87d  jnz     loc_14000B9C5
0x14000b883  cmp     qword ptr [rbx+50h], 0
0x14000b888  jz      short loc_14000B8F7
0x14000b88a  mov     eax, [rsp+68h+arg_20]
0x14000b891  mov     dword ptr [rsp+68h+var_40+4], eax
0x14000b895  mov     dword ptr [rsp+68h+var_40], 0
0x14000b89d  call    cs:__imp_PsGetCurrentProcessId
0x14000b8a4  nop     dword ptr [rax+rax+00h]
0x14000b8a9  mov     rcx, [rbx+50h]; this
0x14000b8ad  lea     rdx, [rsp+68h+var_40]; struct PCW_REPLYITEM_BUFFER *
0x14000b8b2  mov     r8, r14; void *
0x14000b8b5  mov     dword ptr [rsp+68h+var_40+8], eax
0x14000b8b9  mov     dword ptr [rsp+68h+var_40+0Ch], esi
0x14000b8bd  call    ?Complete@PCW_NOTIFICATION@@QEAAJPEAUPCW_REPLYITEM_BUFFER@@PEBX@Z; PCW_NOTIFICATION::Complete(PCW_REPLYITEM_BUFFER *,void const *)
0x14000b8c2  mov     r8, [rbx+50h]
0x14000b8c6  mov     r14d, eax
0x14000b8c9  mov     qword ptr [rbx+50h], 0
0x14000b8d1  test    r8, r8
0x14000b8d4  jz      short loc_14000B8FA
0x14000b8d6  or      ecx, 0FFFFFFFFh
0x14000b8d9  lock xadd [r8+4Ch], ecx
0x14000b8df  cmp     ecx, 1
0x14000b8e2  jnz     short loc_14000B8FA
0x14000b8e4  xor     edx, edx; Tag
0x14000b8e6  mov     rcx, r8; P
0x14000b8e9  call    cs:__imp_ExFreePoolWithTag
0x14000b8f0  nop     dword ptr [rax+rax+00h]
0x14000b8f5  jmp     short loc_14000B8FA
0x14000b8f7  xor     r14d, r14d
0x14000b8fa  mov     al, [rbx+5Dh]
0x14000b8fd  mov     byte ptr [rbx+5Fh], 0
0x14000b901  mov     [rdi], al
0x14000b903  cmp     byte ptr [rbx+5Dh], 0
0x14000b907  jnz     short loc_14000B91B
0x14000b909  cmp     byte ptr [rbx+5Eh], 0
0x14000b90d  jz      short loc_14000B940
0x14000b90f  mov     rcx, rbx; this
0x14000b912  mov     byte ptr [rbx+5Eh], 0
0x14000b916  call    ?DeliverGenericDisconnectNotification@PCW_USER_REGISTRATION@@AEAAXXZ; PCW_USER_REGISTRATION::DeliverGenericDisconnectNotification(void)
0x14000b91b  xor     edx, edx
0x14000b91d  mov     rcx, rbp
0x14000b920  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b927  nop     dword ptr [rax+rax+00h]
0x14000b92c  call    cs:__imp_KeLeaveCriticalRegion
0x14000b933  nop     dword ptr [rax+rax+00h]
0x14000b938  mov     eax, r14d
0x14000b93b  jmp     loc_14000B9E7
0x14000b940  lea     rsi, [rbx+40h]
0x14000b944  mov     rcx, [rsi]; P
0x14000b947  cmp     rcx, rsi
0x14000b94a  jz      short loc_14000B91B
0x14000b94c  cmp     [rcx+8], rsi
0x14000b950  jnz     short loc_14000B9BE
0x14000b952  mov     rax, [rcx]
0x14000b955  cmp     [rax+8], rcx
0x14000b959  jnz     short loc_14000B9BE
0x14000b95b  mov     [rsi], rax
0x14000b95e  mov     [rax+8], rsi
0x14000b962  mov     rdi, [rcx+10h]
0x14000b966  mov     qword ptr [rcx+10h], 0
0x14000b96e  test    rcx, rcx
0x14000b971  jz      short loc_14000B981
0x14000b973  xor     edx, edx; Tag
0x14000b975  call    cs:__imp_ExFreePoolWithTag
0x14000b97c  nop     dword ptr [rax+rax+00h]
0x14000b981  cmp     byte ptr [rdi+44h], 0
0x14000b985  jz      short loc_14000B9A7
0x14000b987  or      eax, 0FFFFFFFFh
0x14000b98a  lock xadd [rdi+4Ch], eax
0x14000b98f  cmp     eax, 1
0x14000b992  jnz     short loc_14000B944
0x14000b994  xor     edx, edx; Tag
0x14000b996  mov     rcx, rdi; P
0x14000b999  call    cs:__imp_ExFreePoolWithTag
0x14000b9a0  nop     dword ptr [rax+rax+00h]
0x14000b9a5  jmp     short loc_14000B944
0x14000b9a7  lea     rdx, [rsp+68h+var_48]
0x14000b9ac  mov     [rsp+68h+var_48], rdi
0x14000b9b1  mov     rcx, rbx
0x14000b9b4  call    ?DeliverNotification@PCW_USER_REGISTRATION@@AEAAXV?$unique_ptr@VPCW_NOTIFICATION@@U?$ReleaseDeleter@VPCW_NOTIFICATION@@@@@utl@@@Z; PCW_USER_REGISTRATION::DeliverNotification(utl::unique_ptr<PCW_NOTIFICATION,ReleaseDeleter<PCW_NOTIFICATION>>)
0x14000b9b9  jmp     loc_14000B91B
0x14000b9be  mov     ecx, 3
0x14000b9c3  int     29h; Win8: RtlFailFast(ecx)
0x14000b9c5  xor     edx, edx
0x14000b9c7  mov     rcx, rbp
0x14000b9ca  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b9d1  nop     dword ptr [rax+rax+00h]
0x14000b9d6  call    cs:__imp_KeLeaveCriticalRegion
0x14000b9dd  nop     dword ptr [rax+rax+00h]
0x14000b9e2  mov     eax, 0C0000184h
0x14000b9e7  mov     rcx, [rsp+68h+var_30]
0x14000b9ec  xor     rcx, rsp; StackCookie
0x14000b9ef  call    __security_check_cookie
0x14000b9f4  add     rsp, 40h
0x14000b9f8  pop     r14
0x14000b9fa  pop     rdi
0x14000b9fb  pop     rsi
0x14000b9fc  pop     rbp
0x14000b9fd  pop     rbx
0x14000b9fe  retn
```
