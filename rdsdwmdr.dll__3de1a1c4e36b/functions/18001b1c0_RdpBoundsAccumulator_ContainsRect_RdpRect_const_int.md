# RdpBoundsAccumulator::ContainsRect(RdpRect const *,int *)

- ea: `0x18001b1c0`
- end: `0x18001b3cf`
- name: `?ContainsRect@RdpBoundsAccumulator@@UEBAJPEBURdpRect@@PEAH@Z`
- size: `527`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct RdpRect *, int *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001b1c0`
- `0x18001ce74`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001b384`: `pTargetBACopy->RemoveBA failed`
- `0x18001b33a`: `pTargetBACopy->AddRect failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::ContainsRect(
        RdpBoundsAccumulator *this,
        const struct RdpRect *a2,
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
  __int64 v17; // rsi
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
    v8 = 27;
    v9 = "pRect";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      ActivityIdPrefix,
      (__int64)v9);
LABEL_7:
    v10 = -2147467261;
    goto LABEL_30;
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
    v8 = 28;
    v9 = "pResult";
    goto LABEL_6;
  }
  *a3 = 0;
  v10 = RgnlibBA_CreateInstance(&v25);
  if ( v10 >= 0 )
  {
    v17 = v25;
    v10 = (*(__int64 (__fastcall **)(__int64, const struct RdpRect *))(*(_QWORD *)v25 + 40LL))(v25, a2);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, RdpBoundsAccumulator *))(*(_QWORD *)v17 + 56LL))(v17, this);
      if ( v10 >= 0 )
      {
        *a3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 136LL))(v17);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v21, v22, v23);
        v15 = 31;
        v16 = "pTargetBACopy->RemoveBA failed";
        goto LABEL_18;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v18, v19, v20);
      v15 = 30;
      v16 = "pTargetBACopy->AddRect failed";
      goto LABEL_18;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
    v15 = 29;
    v16 = "failed to get workItem BA";
LABEL_18:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      v14,
      (__int64)v16,
      v10);
  }
LABEL_30:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001b1c0  mov     [rsp+arg_0], rbx
0x18001b1c5  mov     [rsp+arg_10], rbp
0x18001b1ca  push    rsi
0x18001b1cb  push    rdi
0x18001b1cc  push    r14
0x18001b1ce  sub     rsp, 30h
0x18001b1d2  mov     [rsp+48h+arg_8], 0
0x18001b1db  mov     rdi, r8
0x18001b1de  mov     rbp, rdx
0x18001b1e1  mov     r14, rcx
0x18001b1e4  test    rdx, rdx
0x18001b1e7  jnz     short loc_18001B240
0x18001b1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1f0  lea     rax, WPP_GLOBAL_Control
0x18001b1f7  cmp     rcx, rax
0x18001b1fa  jz      short loc_18001B236
0x18001b1fc  test    byte ptr [rcx+1Ch], 8
0x18001b200  jz      short loc_18001B236
0x18001b202  cmp     byte ptr [rcx+19h], 2
0x18001b206  jb      short loc_18001B236
0x18001b208  call    RdpX_GetActivityIdPrefix
0x18001b20d  lea     edx, [rbp+1Bh]
0x18001b210  lea     rcx, aPrect; "pRect"
0x18001b217  mov     [rsp+48h+var_28], rcx
0x18001b21c  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001b223  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b22a  mov     r9d, eax
0x18001b22d  mov     rcx, [rcx+10h]
0x18001b231  call    WPP_SF_Ds
0x18001b236  mov     ebx, 80004003h
0x18001b23b  jmp     loc_18001B3A4
0x18001b240  test    rdi, rdi
0x18001b243  jnz     short loc_18001B275
0x18001b245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b24c  lea     rax, WPP_GLOBAL_Control
0x18001b253  cmp     rcx, rax
0x18001b256  jz      short loc_18001B236
0x18001b258  test    byte ptr [rcx+1Ch], 8
0x18001b25c  jz      short loc_18001B236
0x18001b25e  cmp     byte ptr [rcx+19h], 2
0x18001b262  jb      short loc_18001B236
0x18001b264  call    RdpX_GetActivityIdPrefix
0x18001b269  lea     edx, [rdi+1Ch]
0x18001b26c  lea     rcx, aPresult; "pResult"
0x18001b273  jmp     short loc_18001B217
0x18001b275  lea     rcx, [rsp+48h+arg_8]
0x18001b27a  mov     dword ptr [r8], 0
0x18001b281  call    RgnlibBA_CreateInstance
0x18001b286  mov     ebx, eax
0x18001b288  test    eax, eax
0x18001b28a  jns     short loc_18001B2F0
0x18001b28c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b293  lea     rax, WPP_GLOBAL_Control
0x18001b29a  cmp     rcx, rax
0x18001b29d  jz      loc_18001B3A4
0x18001b2a3  test    byte ptr [rcx+1Ch], 8
0x18001b2a7  jz      loc_18001B3A4
0x18001b2ad  cmp     byte ptr [rcx+19h], 2
0x18001b2b1  jb      loc_18001B3A4
0x18001b2b7  call    RdpX_GetActivityIdPrefix
0x18001b2bc  mov     edx, 1Dh
0x18001b2c1  lea     rcx, aFailedToGetWor; "failed to get workItem BA"
0x18001b2c8  mov     [rsp+48h+var_20], ebx
0x18001b2cc  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001b2d3  mov     [rsp+48h+var_28], rcx
0x18001b2d8  mov     r9d, eax
0x18001b2db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2e2  mov     rcx, [rcx+10h]
0x18001b2e6  call    WPP_SF_DsD
0x18001b2eb  jmp     loc_18001B3A4
0x18001b2f0  mov     rsi, [rsp+48h+arg_8]
0x18001b2f5  mov     rdx, rbp
0x18001b2f8  mov     rcx, rsi
0x18001b2fb  mov     rax, [rsi]
0x18001b2fe  mov     rax, [rax+28h]
0x18001b302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b307  mov     ebx, eax
0x18001b309  test    eax, eax
0x18001b30b  jns     short loc_18001B343
0x18001b30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b314  lea     rax, WPP_GLOBAL_Control
0x18001b31b  cmp     rcx, rax
0x18001b31e  jz      loc_18001B3A4
0x18001b324  test    byte ptr [rcx+1Ch], 8
0x18001b328  jz      short loc_18001B3A4
0x18001b32a  cmp     byte ptr [rcx+19h], 2
0x18001b32e  jb      short loc_18001B3A4
0x18001b330  call    RdpX_GetActivityIdPrefix
0x18001b335  mov     edx, 1Eh
0x18001b33a  lea     rcx, aPtargetbacopyA; "pTargetBACopy->AddRect failed"
0x18001b341  jmp     short loc_18001B2C8
0x18001b343  mov     rax, [rsi]
0x18001b346  mov     rdx, r14
0x18001b349  mov     rcx, rsi
0x18001b34c  mov     rax, [rax+38h]
0x18001b350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b355  mov     ebx, eax
0x18001b357  test    eax, eax
0x18001b359  jns     short loc_18001B390
0x18001b35b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b362  lea     rax, WPP_GLOBAL_Control
0x18001b369  cmp     rcx, rax
0x18001b36c  jz      short loc_18001B3A4
0x18001b36e  test    byte ptr [rcx+1Ch], 8
0x18001b372  jz      short loc_18001B3A4
0x18001b374  cmp     byte ptr [rcx+19h], 2
0x18001b378  jb      short loc_18001B3A4
0x18001b37a  call    RdpX_GetActivityIdPrefix
0x18001b37f  mov     edx, 1Fh
0x18001b384  lea     rcx, aPtargetbacopyR; "pTargetBACopy->RemoveBA failed"
0x18001b38b  jmp     loc_18001B2C8
0x18001b390  mov     rax, [rsi]
0x18001b393  mov     rcx, rsi
0x18001b396  mov     rax, [rax+88h]
0x18001b39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3a2  mov     [rdi], eax
0x18001b3a4  mov     rcx, [rsp+48h+arg_8]
0x18001b3a9  test    rcx, rcx
0x18001b3ac  jz      short loc_18001B3BA
0x18001b3ae  mov     rax, [rcx]
0x18001b3b1  mov     rax, [rax+10h]
0x18001b3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3ba  mov     rbp, [rsp+48h+arg_10]
0x18001b3bf  mov     eax, ebx
0x18001b3c1  mov     rbx, [rsp+48h+arg_0]
0x18001b3c6  add     rsp, 30h
0x18001b3ca  pop     r14
0x18001b3cc  pop     rdi
0x18001b3cd  pop     rsi
0x18001b3ce  retn
```
