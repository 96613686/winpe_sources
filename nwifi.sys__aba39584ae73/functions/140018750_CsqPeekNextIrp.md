# CsqPeekNextIrp

- ea: `0x140018750`
- end: `0x1400188f6`
- name: `CsqPeekNextIrp`
- size: `422`
- prototype: `IO_CSQ_PEEK_NEXT_IRP`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140018750`
- `0x140018b04`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140018827`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140018827`
- `ntoskrnl!ExAllocatePool2` at `0x14001883c`
- `ntoskrnl!ExAllocatePool2` at `0x14001883c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018895`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018895`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400188a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400188a6`

## pseudocode

```c
_LIST_ENTRY **__fastcall CsqPeekNextIrp(char *Csq, PIRP Irp, _DWORD *PeekContext)
{
  _LIST_ENTRY *v4; // r8
  _LIST_ENTRY *Flink; // rax
  int v8; // r14d
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _QWORD *v12; // rdi
  int v13; // ebx
  void (__fastcall *v14)(_IO_CSQ *, _IRP *); // rcx
  int v15; // [rsp+50h] [rbp+8h] BYREF
  int v16; // [rsp+58h] [rbp+10h] BYREF

  v16 = 0;
  v15 = 0;
  v4 = (_LIST_ENTRY *)(Csq + 88);
  if ( Irp )
    Flink = Irp->Tail.Overlay.ListEntry.Flink;
  else
    Flink = v4->Flink;
  if ( Flink == v4 )
  {
    if ( !PeekContext )
      return 0;
    Dot11UpcallCopyReqToBuffer(*(_QWORD *)PeekContext, 0, 0, (unsigned int)&v16, (__int64)&v15);
    v8 = v15;
    v9 = v15 + 32;
    if ( (unsigned int)(v15 + 32) < 0x10 )
      goto LABEL_29;
    if ( v9 > 0x40 )
    {
      if ( v9 > 0x100 )
      {
        if ( v9 > 0x400 )
        {
          if ( v9 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 1986622327);
LABEL_20:
            if ( Pool2 )
            {
              Pool2[2] = 1986622327;
              v12 = Pool2 + 4;
              *(_QWORD *)Pool2 = p_WaitListHead;
              v13 = Dot11UpcallCopyReqToBuffer(*(_QWORD *)PeekContext, v8, (int)Pool2 + 32, (unsigned int)&v16, 0);
              if ( v13 >= 0 )
              {
                v14 = (void (__fastcall *)(_IO_CSQ *, _IRP *))*((_QWORD *)Csq + 14);
                if ( *(char **)v14 != Csq + 104 )
                  __fastfail(3u);
                *v12 = Csq + 104;
                v12[1] = v14;
                *(_QWORD *)v14 = v12;
                *((_QWORD *)Csq + 14) = v12;
              }
              else if ( v12 )
              {
                if ( *(v12 - 2) )
                  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(v12 - 2), v12 - 2);
                else
                  ExFreePoolWithTag(v12 - 2, *((_DWORD *)v12 - 2));
              }
              goto LABEL_30;
            }
LABEL_29:
            v13 = -1073741670;
LABEL_30:
            PeekContext[2] = v13;
            return 0;
          }
          p_WaitListHead = &stru_1400B31C0;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_20;
  }
  if ( PeekContext )
    PeekContext[2] = -1073741802;
  return &Flink[-11].Blink;
}

```

## disassembly

```asm
0x140018750  mov     rax, rsp
0x140018753  mov     [rax+18h], rbx
0x140018757  mov     [rax+20h], rbp
0x14001875b  push    rsi
0x14001875c  push    rdi
0x14001875d  push    r14
0x14001875f  sub     rsp, 30h
0x140018763  mov     dword ptr [rax+10h], 0
0x14001876a  mov     rsi, r8
0x14001876d  mov     dword ptr [rax+8], 0
0x140018774  lea     r8, [rcx+58h]
0x140018778  mov     rbp, rcx
0x14001877b  test    rdx, rdx
0x14001877e  jnz     short loc_140018785
0x140018780  mov     rax, [r8]
0x140018783  jmp     short loc_14001878C
0x140018785  mov     rax, [rdx+0A8h]
0x14001878c  cmp     rax, r8
0x14001878f  jz      short loc_1400187A8
0x140018791  test    rsi, rsi
0x140018794  jz      short loc_14001879D
0x140018796  mov     dword ptr [rsi+8], 0C0000016h
0x14001879d  add     rax, 0FFFFFFFFFFFFFF58h
0x1400187a3  jmp     loc_1400188E2
0x1400187a8  test    rsi, rsi
0x1400187ab  jz      loc_1400188E0
0x1400187b1  mov     rcx, [rsi]
0x1400187b4  lea     rax, [rsp+48h+arg_0]
0x1400187b9  lea     r9, [rsp+48h+arg_8]
0x1400187be  mov     [rsp+48h+var_28], rax
0x1400187c3  xor     r8d, r8d
0x1400187c6  xor     edx, edx
0x1400187c8  call    Dot11UpcallCopyReqToBuffer
0x1400187cd  mov     r14d, [rsp+48h+arg_0]
0x1400187d2  lea     eax, [r14+20h]
0x1400187d6  cmp     eax, 10h
0x1400187d9  jb      loc_1400188D8
0x1400187df  mov     ecx, 40h ; '@'
0x1400187e4  mov     edi, 76697377h
0x1400187e9  cmp     eax, ecx
0x1400187eb  ja      short loc_1400187F6
0x1400187ed  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400187f4  jmp     short loc_140018824
0x1400187f6  cmp     eax, 100h
0x1400187fb  ja      short loc_140018806
0x1400187fd  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140018804  jmp     short loc_140018824
0x140018806  cmp     eax, 400h
0x14001880b  ja      short loc_140018816
0x14001880d  lea     rbx, Lookaside
0x140018814  jmp     short loc_140018824
0x140018816  cmp     eax, 800h
0x14001881b  ja      short loc_140018835
0x14001881d  lea     rbx, stru_1400B31C0
0x140018824  mov     rcx, rbx; Lookaside
0x140018827  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001882e  nop     dword ptr [rax+rax+00h]
0x140018833  jmp     short loc_140018848
0x140018835  xor     ebx, ebx
0x140018837  mov     edx, eax
0x140018839  mov     r8d, edi
0x14001883c  call    cs:__imp_ExAllocatePool2
0x140018843  nop     dword ptr [rax+rax+00h]
0x140018848  test    rax, rax
0x14001884b  jz      loc_1400188D8
0x140018851  mov     [rax+8], edi
0x140018854  lea     r9, [rsp+48h+arg_8]
0x140018859  lea     rdi, [rax+10h]
0x14001885d  mov     [rax], rbx
0x140018860  mov     rcx, [rsi]
0x140018863  lea     r8, [rdi+10h]
0x140018867  mov     edx, r14d
0x14001886a  mov     [rsp+48h+var_28], 0
0x140018873  call    Dot11UpcallCopyReqToBuffer
0x140018878  mov     ebx, eax
0x14001887a  test    eax, eax
0x14001887c  jns     short loc_1400188B4
0x14001887e  test    rdi, rdi
0x140018881  jz      short loc_1400188DD
0x140018883  lea     rcx, [rdi-10h]; P
0x140018887  mov     rax, [rcx]
0x14001888a  test    rax, rax
0x14001888d  jz      short loc_1400188A3
0x14001888f  mov     rdx, rcx; Entry
0x140018892  mov     rcx, rax; Lookaside
0x140018895  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001889c  nop     dword ptr [rax+rax+00h]
0x1400188a1  jmp     short loc_1400188DD
0x1400188a3  mov     edx, [rcx+8]; Tag
0x1400188a6  call    cs:__imp_ExFreePoolWithTag
0x1400188ad  nop     dword ptr [rax+rax+00h]
0x1400188b2  jmp     short loc_1400188DD
0x1400188b4  lea     rax, [rbp+68h]
0x1400188b8  mov     rcx, [rax+8]
0x1400188bc  cmp     [rcx], rax
0x1400188bf  jz      short loc_1400188C8
0x1400188c1  mov     ecx, 3
0x1400188c6  int     29h; Win8: RtlFailFast(ecx)
0x1400188c8  mov     [rdi], rax
0x1400188cb  mov     [rdi+8], rcx
0x1400188cf  mov     [rcx], rdi
0x1400188d2  mov     [rax+8], rdi
0x1400188d6  jmp     short loc_1400188DD
0x1400188d8  mov     ebx, 0C000009Ah
0x1400188dd  mov     [rsi+8], ebx
0x1400188e0  xor     eax, eax
0x1400188e2  mov     rbx, [rsp+48h+arg_10]
0x1400188e7  mov     rbp, [rsp+48h+arg_18]
0x1400188ec  add     rsp, 30h
0x1400188f0  pop     r14
0x1400188f2  pop     rdi
0x1400188f3  pop     rsi
0x1400188f4  retn
```
