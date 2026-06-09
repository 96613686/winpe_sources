# RdpBoundsAccumulator::IsSubsetOfBA(IRdpBoundsAccumulator const *,int *)

- ea: `0x18001c3c0`
- end: `0x18001c5e9`
- name: `?IsSubsetOfBA@RdpBoundsAccumulator@@UEBAJPEBVIRdpBoundsAccumulator@@PEAH@Z`
- size: `553`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct IRdpBoundsAccumulator *, int *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001c3c0`
- `0x18001ce74`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001c553`: `spTargetBACopy->AddBA failed`
- `0x18001c59d`: `pTargetBACopy->RemoveBA failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::IsSubsetOfBA(
        RdpBoundsAccumulator *this,
        const struct IRdpBoundsAccumulator *a2,
        int *a3,
        __int64 a4)
{
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v25; // [rsp+58h] [rbp+10h] BYREF

  v25 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0, a3, a4);
    v8 = 22;
    v9 = "pSource";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      ActivityIdPrefix,
      (__int64)v9);
LABEL_7:
    v10 = -2147467261;
    goto LABEL_31;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, 0, a4);
    v8 = 23;
    v9 = "pResult";
    goto LABEL_6;
  }
  v10 = 0;
  *a3 = 0;
  if ( !(*(unsigned int (__fastcall **)(const struct IRdpBoundsAccumulator *))(*(_QWORD *)a2 + 136LL))(a2) )
  {
    v10 = RgnlibBA_CreateInstance(&v25);
    if ( v10 >= 0 )
    {
      v17 = v25;
      v10 = (*(__int64 (__fastcall **)(__int64, RdpBoundsAccumulator *))(*(_QWORD *)v25 + 48LL))(v25, this);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, const struct IRdpBoundsAccumulator *))(*(_QWORD *)v17 + 56LL))(
                v17,
                a2);
        if ( v10 >= 0 )
        {
          *a3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 136LL))(v17);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v21, v22, v23);
          v15 = 26;
          v16 = "pTargetBACopy->RemoveBA failed";
          goto LABEL_19;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v18, v19, v20);
        v15 = 25;
        v16 = "spTargetBACopy->AddBA failed";
        goto LABEL_19;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
      v15 = 24;
      v16 = "failed to get workItem BA";
LABEL_19:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
        v14,
        (__int64)v16,
        v10);
    }
  }
LABEL_31:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c3c0  mov     [rsp+arg_0], rbx
0x18001c3c5  mov     [rsp+arg_10], rbp
0x18001c3ca  push    rsi
0x18001c3cb  push    rdi
0x18001c3cc  push    r14
0x18001c3ce  sub     rsp, 30h
0x18001c3d2  mov     [rsp+48h+arg_8], 0
0x18001c3db  mov     r14, r8
0x18001c3de  mov     rsi, rdx
0x18001c3e1  mov     rbp, rcx
0x18001c3e4  test    rdx, rdx
0x18001c3e7  jnz     short loc_18001C440
0x18001c3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3f0  lea     rax, WPP_GLOBAL_Control
0x18001c3f7  cmp     rcx, rax
0x18001c3fa  jz      short loc_18001C436
0x18001c3fc  test    byte ptr [rcx+1Ch], 8
0x18001c400  jz      short loc_18001C436
0x18001c402  cmp     byte ptr [rcx+19h], 2
0x18001c406  jb      short loc_18001C436
0x18001c408  call    RdpX_GetActivityIdPrefix
0x18001c40d  lea     edx, [rsi+16h]
0x18001c410  lea     rcx, aPsource; "pSource"
0x18001c417  mov     [rsp+48h+var_28], rcx
0x18001c41c  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c423  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c42a  mov     r9d, eax
0x18001c42d  mov     rcx, [rcx+10h]
0x18001c431  call    WPP_SF_Ds
0x18001c436  mov     ebx, 80004003h
0x18001c43b  jmp     loc_18001C5BE
0x18001c440  test    r14, r14
0x18001c443  jnz     short loc_18001C476
0x18001c445  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c44c  lea     rax, WPP_GLOBAL_Control
0x18001c453  cmp     rcx, rax
0x18001c456  jz      short loc_18001C436
0x18001c458  test    byte ptr [rcx+1Ch], 8
0x18001c45c  jz      short loc_18001C436
0x18001c45e  cmp     byte ptr [rcx+19h], 2
0x18001c462  jb      short loc_18001C436
0x18001c464  call    RdpX_GetActivityIdPrefix
0x18001c469  lea     edx, [r14+17h]
0x18001c46d  lea     rcx, aPresult; "pResult"
0x18001c474  jmp     short loc_18001C417
0x18001c476  xor     ebx, ebx
0x18001c478  mov     rcx, rsi
0x18001c47b  mov     [r8], ebx
0x18001c47e  mov     rax, [rdx]
0x18001c481  mov     rax, [rax+88h]
0x18001c488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c48d  test    eax, eax
0x18001c48f  jnz     loc_18001C5BE
0x18001c495  lea     rcx, [rsp+48h+arg_8]
0x18001c49a  call    RgnlibBA_CreateInstance
0x18001c49f  mov     ebx, eax
0x18001c4a1  test    eax, eax
0x18001c4a3  jns     short loc_18001C509
0x18001c4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4ac  lea     rax, WPP_GLOBAL_Control
0x18001c4b3  cmp     rcx, rax
0x18001c4b6  jz      loc_18001C5BE
0x18001c4bc  test    byte ptr [rcx+1Ch], 8
0x18001c4c0  jz      loc_18001C5BE
0x18001c4c6  cmp     byte ptr [rcx+19h], 2
0x18001c4ca  jb      loc_18001C5BE
0x18001c4d0  call    RdpX_GetActivityIdPrefix
0x18001c4d5  mov     edx, 18h
0x18001c4da  lea     rcx, aFailedToGetWor; "failed to get workItem BA"
0x18001c4e1  mov     [rsp+48h+var_20], ebx
0x18001c4e5  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c4ec  mov     [rsp+48h+var_28], rcx
0x18001c4f1  mov     r9d, eax
0x18001c4f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4fb  mov     rcx, [rcx+10h]
0x18001c4ff  call    WPP_SF_DsD
0x18001c504  jmp     loc_18001C5BE
0x18001c509  mov     rdi, [rsp+48h+arg_8]
0x18001c50e  mov     rdx, rbp
0x18001c511  mov     rcx, rdi
0x18001c514  mov     rax, [rdi]
0x18001c517  mov     rax, [rax+30h]
0x18001c51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c520  mov     ebx, eax
0x18001c522  test    eax, eax
0x18001c524  jns     short loc_18001C55C
0x18001c526  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c52d  lea     rax, WPP_GLOBAL_Control
0x18001c534  cmp     rcx, rax
0x18001c537  jz      loc_18001C5BE
0x18001c53d  test    byte ptr [rcx+1Ch], 8
0x18001c541  jz      short loc_18001C5BE
0x18001c543  cmp     byte ptr [rcx+19h], 2
0x18001c547  jb      short loc_18001C5BE
0x18001c549  call    RdpX_GetActivityIdPrefix
0x18001c54e  mov     edx, 19h
0x18001c553  lea     rcx, aSptargetbacopy; "spTargetBACopy->AddBA failed"
0x18001c55a  jmp     short loc_18001C4E1
0x18001c55c  mov     rax, [rdi]
0x18001c55f  mov     rdx, rsi
0x18001c562  mov     rcx, rdi
0x18001c565  mov     rax, [rax+38h]
0x18001c569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c56e  mov     ebx, eax
0x18001c570  test    eax, eax
0x18001c572  jns     short loc_18001C5A9
0x18001c574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c57b  lea     rax, WPP_GLOBAL_Control
0x18001c582  cmp     rcx, rax
0x18001c585  jz      short loc_18001C5BE
0x18001c587  test    byte ptr [rcx+1Ch], 8
0x18001c58b  jz      short loc_18001C5BE
0x18001c58d  cmp     byte ptr [rcx+19h], 2
0x18001c591  jb      short loc_18001C5BE
0x18001c593  call    RdpX_GetActivityIdPrefix
0x18001c598  mov     edx, 1Ah
0x18001c59d  lea     rcx, aPtargetbacopyR; "pTargetBACopy->RemoveBA failed"
0x18001c5a4  jmp     loc_18001C4E1
0x18001c5a9  mov     rax, [rdi]
0x18001c5ac  mov     rcx, rdi
0x18001c5af  mov     rax, [rax+88h]
0x18001c5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5bb  mov     [r14], eax
0x18001c5be  mov     rcx, [rsp+48h+arg_8]
0x18001c5c3  test    rcx, rcx
0x18001c5c6  jz      short loc_18001C5D4
0x18001c5c8  mov     rax, [rcx]
0x18001c5cb  mov     rax, [rax+10h]
0x18001c5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5d4  mov     rbp, [rsp+48h+arg_10]
0x18001c5d9  mov     eax, ebx
0x18001c5db  mov     rbx, [rsp+48h+arg_0]
0x18001c5e0  add     rsp, 30h
0x18001c5e4  pop     r14
0x18001c5e6  pop     rdi
0x18001c5e7  pop     rsi
0x18001c5e8  retn
```
