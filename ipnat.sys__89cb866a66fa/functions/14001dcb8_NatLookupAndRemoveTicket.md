# NatLookupAndRemoveTicket

- ea: `0x14001dcb8`
- end: `0x14001df03`
- name: `NatLookupAndRemoveTicket`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002665c`

## callees

- `0x1400021bc`
- `0x140006e18`
- `0x14001c92c`
- `0x14001dcb8`
- `0x14001ee34`

## pseudocode

```c
__int64 __fastcall NatLookupAndRemoveTicket(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _DWORD *a6,
        _WORD *a7)
{
  _DWORD *v10; // r12
  _DWORD *v11; // rbx
  int v12; // r15d
  unsigned __int64 v13; // rdi
  unsigned __int16 v14; // bp
  __int64 v15; // rdx
  int v16; // eax
  __int16 v17; // cx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_iid(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a2, a3);
  }
  v10 = (_DWORD *)(a1 + 168);
  v11 = *(_DWORD **)(a1 + 168);
  v12 = 0;
  v13 = HIDWORD(a2);
  v14 = HIBYTE(WORD2(a2)) | (BYTE4(a2) << 8);
  while ( 1 )
  {
    if ( v11 == v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
      }
      return 3221225473LL;
    }
    v15 = (unsigned int)v11[12];
    if ( (v15 & 4) != 0 )
    {
      if ( v14 > *((_WORD *)v11 + 22) || v14 < _byteswap_ushort(*((_WORD *)v11 + 10)) )
        goto LABEL_23;
    }
    else if ( a2 != *((_QWORD *)v11 + 2) )
    {
      goto LABEL_23;
    }
    if ( a3 == *((_QWORD *)v11 + 3)
      || ((v16 = v11[6]) == 0 || v16 == (_DWORD)a3) && ((v17 = *((_WORD *)v11 + 14)) == 0 || v17 == WORD2(a3)) )
    {
      if ( (v15 & 8) != 0 )
      {
        v12 = NatCheckIsCustomLifetimeTicketValid(v11, v15, 0);
        if ( v12 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              64,
              WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids,
              (unsigned int)v12);
          }
        }
      }
      if ( v12 >= 0 )
        break;
    }
LABEL_23:
    v11 = *(_DWORD **)v11;
  }
  *a5 = *((_QWORD *)v11 + 4);
  *a6 = v11[10];
  if ( (v11[12] & 4) == 0 )
    LOWORD(v13) = *((_WORD *)v11 + 22);
  *a7 = v13;
  if ( (v11[12] & 1) != 0 )
  {
    v21 = *((_QWORD *)v11 + 4);
    if ( *(int *)(v21 + 72) >= 0 )
      _InterlockedIncrement((volatile signed __int32 *)(v21 + 76));
  }
  else
  {
    _InterlockedDecrement(&TicketCount);
    v19 = *(_QWORD *)v11;
    if ( *(_DWORD **)(*(_QWORD *)v11 + 8LL) != v11 || (v20 = (_QWORD *)*((_QWORD *)v11 + 1), (_DWORD *)*v20 != v11) )
      __fastfail(3u);
    *v20 = v19;
    *(_QWORD *)(v19 + 8) = v20;
    NatFreeBlockAndUpdateStateAllocationUsage(&TicketLookasideList, v11, 64);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001dcb8  push    rbx
0x14001dcba  push    rbp
0x14001dcbb  push    rsi
0x14001dcbc  push    rdi
0x14001dcbd  push    r12
0x14001dcbf  push    r14
0x14001dcc1  push    r15
0x14001dcc3  sub     rsp, 30h
0x14001dcc7  mov     rsi, r8
0x14001dcca  mov     r14, rdx
0x14001dccd  mov     rbx, rcx
0x14001dcd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dcd7  lea     rax, WPP_GLOBAL_Control
0x14001dcde  cmp     rcx, rax
0x14001dce1  jz      short loc_14001DD01
0x14001dce3  mov     eax, [rcx+2Ch]
0x14001dce6  test    al, 1
0x14001dce8  jz      short loc_14001DD01
0x14001dcea  cmp     byte ptr [rcx+29h], 6
0x14001dcee  jb      short loc_14001DD01
0x14001dcf0  mov     rcx, [rcx+18h]
0x14001dcf4  mov     r9, rdx
0x14001dcf7  mov     [rsp+68h+var_48], r8
0x14001dcfc  call    WPP_SF_iid
0x14001dd01  mov     rdi, r14
0x14001dd04  lea     r12, [rbx+0A8h]
0x14001dd0b  mov     rbx, [r12]
0x14001dd0f  xor     r15d, r15d
0x14001dd12  shr     rdi, 20h
0x14001dd16  movzx   ebp, dil
0x14001dd1a  movzx   eax, di
0x14001dd1d  shl     bp, 8
0x14001dd21  shr     ax, 8
0x14001dd25  or      bp, ax
0x14001dd28  jmp     loc_14001DDE6
0x14001dd2d  mov     edx, [rbx+30h]
0x14001dd30  test    dl, 4
0x14001dd33  jz      short loc_14001DD59
0x14001dd35  cmp     bp, [rbx+2Ch]
0x14001dd39  ja      loc_14001DDE3
0x14001dd3f  movzx   ecx, byte ptr [rbx+14h]
0x14001dd43  movzx   eax, byte ptr [rbx+15h]
0x14001dd47  shl     cx, 8
0x14001dd4b  or      cx, ax
0x14001dd4e  cmp     bp, cx
0x14001dd51  jb      loc_14001DDE3
0x14001dd57  jmp     short loc_14001DD63
0x14001dd59  cmp     r14, [rbx+10h]
0x14001dd5d  jnz     loc_14001DDE3
0x14001dd63  xor     r8d, r8d
0x14001dd66  cmp     rsi, [rbx+18h]
0x14001dd6a  jz      short loc_14001DD8C
0x14001dd6c  mov     eax, [rbx+18h]
0x14001dd6f  test    eax, eax
0x14001dd71  jz      short loc_14001DD77
0x14001dd73  cmp     eax, esi
0x14001dd75  jnz     short loc_14001DDE3
0x14001dd77  movzx   ecx, word ptr [rbx+1Ch]
0x14001dd7b  test    cx, cx
0x14001dd7e  jz      short loc_14001DD8C
0x14001dd80  mov     rax, rsi
0x14001dd83  shr     rax, 20h
0x14001dd87  cmp     cx, ax
0x14001dd8a  jnz     short loc_14001DDE3
0x14001dd8c  test    dl, 8
0x14001dd8f  jz      short loc_14001DDDE
0x14001dd91  mov     rcx, rbx
0x14001dd94  call    NatCheckIsCustomLifetimeTicketValid
0x14001dd99  xor     r8d, r8d
0x14001dd9c  mov     r15d, eax
0x14001dd9f  test    eax, eax
0x14001dda1  jz      short loc_14001DDDE
0x14001dda3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddaa  lea     rax, WPP_GLOBAL_Control
0x14001ddb1  cmp     rcx, rax
0x14001ddb4  jz      short loc_14001DDDE
0x14001ddb6  mov     edx, [rcx+2Ch]
0x14001ddb9  test    dl, 1
0x14001ddbc  jz      short loc_14001DDDE
0x14001ddbe  cmp     byte ptr [rcx+29h], 2
0x14001ddc2  jb      short loc_14001DDDE
0x14001ddc4  mov     rcx, [rcx+18h]
0x14001ddc8  lea     edx, [r8+40h]
0x14001ddcc  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001ddd3  mov     r9d, r15d
0x14001ddd6  call    WPP_SF_d
0x14001dddb  xor     r8d, r8d
0x14001ddde  test    r15d, r15d
0x14001dde1  jns     short loc_14001DE3F
0x14001dde3  mov     rbx, [rbx]
0x14001dde6  cmp     rbx, r12
0x14001dde9  jnz     loc_14001DD2D
0x14001ddef  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddf6  lea     rax, WPP_GLOBAL_Control
0x14001ddfd  mov     ebx, 0C0000001h
0x14001de02  cmp     rcx, rax
0x14001de05  jz      short loc_14001DE2D
0x14001de07  mov     edx, [rcx+2Ch]
0x14001de0a  test    dl, 1
0x14001de0d  jz      short loc_14001DE2D
0x14001de0f  cmp     byte ptr [rcx+29h], 6
0x14001de13  jb      short loc_14001DE2D
0x14001de15  mov     rcx, [rcx+18h]
0x14001de19  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001de20  mov     edx, 42h ; 'B'
0x14001de25  mov     r9d, ebx
0x14001de28  call    WPP_SF_d
0x14001de2d  mov     eax, ebx
0x14001de2f  add     rsp, 30h
0x14001de33  pop     r15
0x14001de35  pop     r14
0x14001de37  pop     r12
0x14001de39  pop     rdi
0x14001de3a  pop     rsi
0x14001de3b  pop     rbp
0x14001de3c  pop     rbx
0x14001de3d  retn
0x14001de3f  mov     rax, [rsp+68h+arg_20]
0x14001de47  mov     rcx, [rbx+20h]
0x14001de4b  mov     [rax], rcx
0x14001de4e  mov     rax, [rsp+68h+arg_28]
0x14001de56  mov     ecx, [rbx+28h]
0x14001de59  mov     [rax], ecx
0x14001de5b  mov     eax, [rbx+30h]
0x14001de5e  test    al, 4
0x14001de60  jnz     short loc_14001DE66
0x14001de62  movzx   edi, word ptr [rbx+2Ch]
0x14001de66  mov     rax, [rsp+68h+arg_30]
0x14001de6e  mov     [rax], di
0x14001de71  mov     eax, [rbx+30h]
0x14001de74  test    al, 1
0x14001de76  jnz     short loc_14001DEB6
0x14001de78  lock dec cs:TicketCount
0x14001de7f  mov     rax, [rbx]
0x14001de82  cmp     [rax+8], rbx
0x14001de86  jnz     short loc_14001DEAF
0x14001de88  mov     rcx, [rbx+8]
0x14001de8c  cmp     [rcx], rbx
0x14001de8f  jnz     short loc_14001DEAF
0x14001de91  mov     [rcx], rax
0x14001de94  mov     r8d, 40h ; '@'
0x14001de9a  mov     [rax+8], rcx
0x14001de9e  mov     rdx, rbx; Entry
0x14001dea1  lea     rcx, TicketLookasideList; Lookaside
0x14001dea8  call    NatFreeBlockAndUpdateStateAllocationUsage
0x14001dead  jmp     short loc_14001DEC4
0x14001deaf  mov     ecx, 3
0x14001deb4  int     29h; Win8: RtlFailFast(ecx)
0x14001deb6  mov     rax, [rbx+20h]
0x14001deba  cmp     [rax+48h], r8d
0x14001debe  jl      short loc_14001DEC4
0x14001dec0  lock inc dword ptr [rax+4Ch]
0x14001dec4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001decb  lea     rax, WPP_GLOBAL_Control
0x14001ded2  cmp     rcx, rax
0x14001ded5  jz      short loc_14001DEFC
0x14001ded7  mov     eax, [rcx+2Ch]
0x14001deda  test    al, 1
0x14001dedc  jz      short loc_14001DEFC
0x14001dede  cmp     byte ptr [rcx+29h], 6
0x14001dee2  jb      short loc_14001DEFC
0x14001dee4  mov     rcx, [rcx+18h]
0x14001dee8  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001deef  mov     edx, 41h ; 'A'
0x14001def4  xor     r9d, r9d
0x14001def7  call    WPP_SF_d
0x14001defc  xor     eax, eax
0x14001defe  jmp     loc_14001DE2F
```
