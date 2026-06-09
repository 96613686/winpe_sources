# COSKKeyboardManager::HandleUpdateOSKBasedOnRunningAtModern(bool)

- ea: `0x14001154c`
- end: `0x140011642`
- name: `?HandleUpdateOSKBasedOnRunningAtModern@COSKKeyboardManager@@AEAAX_N@Z`
- size: `246`
- prototype: `void __fastcall(COSKKeyboardManager *__hidden this, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140007f54`
- `0x14000fa10`
- `0x140012620`

## callees

- `0x14000df20`
- `0x140011368`
- `0x1400114f8`
- `0x14001154c`
- `0x140027010`

## pseudocode

```c
void __fastcall COSKKeyboardManager::HandleUpdateOSKBasedOnRunningAtModern(COSKKeyboardManager *this, char a2)
{
  __int64 v3; // rcx
  _BYTE *v5; // rbx
  bool v6; // al
  PVOID *v7; // rcx
  char v8; // al
  int v9; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 33);
  if ( !v3 )
  {
    v5 = (char *)this + 272;
LABEL_6:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v9 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 32LL))(v3, &v9);
  v5 = (char *)this + 272;
  v6 = v9 != 0;
  *((_BYTE *)this + 272) = v9 != 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_9329afad6021354e5db6dcc45420c377_Traceguids, v6);
    goto LABEL_6;
  }
LABEL_7:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_d(v7[2], 25, &WPP_9329afad6021354e5db6dcc45420c377_Traceguids, *((unsigned __int8 *)this + 274));
LABEL_10:
  COSKKeyboardManager::HandleSetKeyEnabledState(this, *((_BYTE *)this + 274), L"SoftKeyboardClearUI", 0x10703u);
  v8 = *v5 == 0;
  if ( v8 != *((_BYTE *)this + 224) )
  {
    *((_BYTE *)this + 224) = v8;
    if ( a2 )
      COSKKeyboardManager::HandleUpdateKeyboardUI(this);
  }
}

```

## disassembly

```asm
0x14001154c  push    rbx
0x14001154e  push    rsi
0x14001154f  push    rdi
0x140011550  push    r14
0x140011552  sub     rsp, 28h
0x140011556  mov     rdi, rcx
0x140011559  lea     r14, WPP_GLOBAL_Control
0x140011560  mov     rcx, [rcx+108h]
0x140011567  mov     sil, dl
0x14001156a  test    rcx, rcx
0x14001156d  jnz     short loc_140011578
0x14001156f  lea     rbx, [rdi+110h]
0x140011576  jmp     short loc_1400115CD
0x140011578  mov     [rsp+48h+arg_0], 0
0x140011580  lea     rdx, [rsp+48h+arg_0]
0x140011585  mov     rax, [rcx]
0x140011588  mov     rax, [rax+20h]
0x14001158c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011591  cmp     [rsp+48h+arg_0], 0
0x140011596  lea     rbx, [rdi+110h]
0x14001159d  setnz   al
0x1400115a0  mov     [rbx], al
0x1400115a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115a9  cmp     rcx, r14
0x1400115ac  jz      short loc_1400115FC
0x1400115ae  test    byte ptr [rcx+1Ch], 10h
0x1400115b2  jz      short loc_1400115D4
0x1400115b4  mov     rcx, [rcx+10h]
0x1400115b8  lea     r8, WPP_9329afad6021354e5db6dcc45420c377_Traceguids
0x1400115bf  movzx   r9d, al
0x1400115c3  mov     edx, 18h
0x1400115c8  call    WPP_SF_d
0x1400115cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115d4  cmp     rcx, r14
0x1400115d7  jz      short loc_1400115FC
0x1400115d9  test    byte ptr [rcx+1Ch], 10h
0x1400115dd  jz      short loc_1400115FC
0x1400115df  movzx   r9d, byte ptr [rdi+112h]
0x1400115e7  lea     r8, WPP_9329afad6021354e5db6dcc45420c377_Traceguids
0x1400115ee  mov     rcx, [rcx+10h]
0x1400115f2  mov     edx, 19h
0x1400115f7  call    WPP_SF_d
0x1400115fc  mov     dl, [rdi+112h]; bool
0x140011602  lea     r8, aSoftkeyboardcl; "SoftKeyboardClearUI"
0x140011609  mov     r9d, 10703h; unsigned int
0x14001160f  mov     rcx, rdi; this
0x140011612  call    ?HandleSetKeyEnabledState@COSKKeyboardManager@@AEAAX_NPEBGK@Z; COSKKeyboardManager::HandleSetKeyEnabledState(bool,ushort const *,ulong)
0x140011617  cmp     byte ptr [rbx], 0
0x14001161a  setz    al
0x14001161d  cmp     al, [rdi+0E0h]
0x140011623  jz      short loc_140011638
0x140011625  mov     [rdi+0E0h], al
0x14001162b  test    sil, sil
0x14001162e  jz      short loc_140011638
0x140011630  mov     rcx, rdi; this
0x140011633  call    ?HandleUpdateKeyboardUI@COSKKeyboardManager@@AEAAXXZ; COSKKeyboardManager::HandleUpdateKeyboardUI(void)
0x140011638  add     rsp, 28h
0x14001163c  pop     r14
0x14001163e  pop     rdi
0x14001163f  pop     rsi
0x140011640  pop     rbx
0x140011641  retn
```
