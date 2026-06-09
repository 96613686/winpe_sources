# FIPreQueryInformationCallback

- ea: `0x140001130`
- end: `0x140001273`
- name: `FIPreQueryInformationCallback`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001130`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400011de`
- `ntoskrnl!PsGetThreadId` at `0x1400011de`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001222`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001222`

## pseudocode

```c
_BOOL8 __fastcall FIPreQueryInformationCallback(unsigned __int64 a1, __int64 a2)
{
  __int64 v3; // rax
  int v5; // ebp
  void (__fastcall *v6)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rdi
  struct _KTHREAD *v8; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v11; // rdx
  __int128 v12; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v13[24]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v14; // [rsp+68h] [rbp-50h] BYREF
  _QWORD v15[2]; // [rsp+78h] [rbp-40h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  memset(v13, 0, sizeof(v13));
  v14 = 0;
  v5 = *(_DWORD *)(v3 + 32);
  v6 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v6 )
  {
    v8 = *(struct _KTHREAD **)(a1 + 8);
    memset(v13, 0, sizeof(v13));
    v12 = a1;
    if ( v8 )
      ThreadId = (unsigned int)PsGetThreadId(v8);
    else
      ThreadId = -1;
    *(_DWORD *)&v13[16] = ThreadId;
    *((_QWORD *)&v12 + 1) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)v13 = *(_QWORD *)(*((_QWORD *)&v12 + 1) + 24LL);
    v15[0] = &v12;
    *(_DWORD *)&v13[20] = v5;
    v15[1] = 40;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v14);
    v11 = &v14;
    if ( ActivityIdCallbackData < 0 )
      v11 = 0;
    v6(*(_QWORD *)(a1 + 8), v15, 1, 0x4000000, 1098, v11);
  }
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140001130  push    rbx
0x140001132  push    rbp
0x140001133  push    rsi
0x140001134  push    rdi
0x140001135  sub     rsp, 98h
0x14000113c  mov     rax, cs:__security_cookie
0x140001143  xor     rax, rsp
0x140001146  mov     [rsp+0B8h+var_30], rax
0x14000114e  xor     eax, eax
0x140001150  xorps   xmm0, xmm0
0x140001153  mov     [rsp+0B8h+var_58], rax
0x140001158  mov     rsi, rdx
0x14000115b  mov     rax, [rcx+10h]
0x14000115f  mov     rbx, rcx
0x140001162  movups  [rsp+0B8h+var_78], xmm0
0x140001167  movups  [rsp+0B8h+var_68], xmm0
0x14000116c  movups  [rsp+0B8h+var_50], xmm0
0x140001171  mov     ebp, [rax+20h]
0x140001174  mov     rax, cs:qword_140009A00
0x14000117b  mov     rdi, [rax+10h]
0x14000117f  test    rdi, rdi
0x140001182  jnz     short loc_1400011B4
0x140001184  mov     rax, cs:qword_140009A00
0x14000118b  mov     rcx, [rax+18h]
0x14000118f  xor     eax, eax
0x140001191  test    rcx, rcx
0x140001194  setz    al
0x140001197  mov     rcx, [rsp+0B8h+var_30]
0x14000119f  xor     rcx, rsp; StackCookie
0x1400011a2  call    __security_check_cookie
0x1400011a7  add     rsp, 98h
0x1400011ae  pop     rdi
0x1400011af  pop     rsi
0x1400011b0  pop     rbp
0x1400011b1  pop     rbx
0x1400011b2  retn
0x1400011b4  mov     rcx, [rcx+8]; Thread
0x1400011b8  mov     qword ptr [rsp+0B8h+var_78+8], 0
0x1400011c1  mov     qword ptr [rsp+0B8h+var_68], 0
0x1400011ca  mov     qword ptr [rsp+0B8h+var_78], rbx
0x1400011cf  movdqu  [rsp+0B8h+var_68+8], xmm0
0x1400011d5  test    rcx, rcx
0x1400011d8  jz      loc_140001269
0x1400011de  call    cs:__imp_PsGetThreadId
0x1400011e5  nop     dword ptr [rax+rax+00h]
0x1400011ea  mov     dword ptr [rsp+0B8h+var_58], eax
0x1400011ee  lea     rdx, [rsp+0B8h+var_50]
0x1400011f3  mov     rax, [rsi+20h]
0x1400011f7  mov     rcx, rbx
0x1400011fa  mov     qword ptr [rsp+0B8h+var_78+8], rax
0x1400011ff  mov     rax, [rax+18h]
0x140001203  mov     qword ptr [rsp+0B8h+var_68], rax
0x140001208  lea     rax, [rsp+0B8h+var_78]
0x14000120d  mov     [rsp+0B8h+var_40], rax
0x140001212  mov     dword ptr [rsp+0B8h+var_58+4], ebp
0x140001216  mov     [rsp+0B8h+var_38], 28h ; '('
0x140001222  call    cs:__imp_FltGetActivityIdCallbackData
0x140001229  nop     dword ptr [rax+rax+00h]
0x14000122e  xor     ecx, ecx
0x140001230  lea     rdx, [rsp+0B8h+var_50]
0x140001235  test    eax, eax
0x140001237  mov     r9d, 4000000h
0x14000123d  mov     r8d, 1
0x140001243  mov     rax, rdi
0x140001246  cmovs   rdx, rcx
0x14000124a  mov     rcx, [rbx+8]
0x14000124e  mov     [rsp+0B8h+var_90], rdx
0x140001253  lea     rdx, [rsp+0B8h+var_40]
0x140001258  mov     [rsp+0B8h+var_98], 44Ah
0x14000125f  call    _guard_dispatch_icall
0x140001264  jmp     loc_140001184
0x140001269  mov     eax, 0FFFFFFFFh
0x14000126e  jmp     loc_1400011EA
```
