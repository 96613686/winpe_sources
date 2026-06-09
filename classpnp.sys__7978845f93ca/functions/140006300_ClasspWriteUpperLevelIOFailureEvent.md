# ClasspWriteUpperLevelIOFailureEvent

- ea: `0x140006300`
- end: `0x1400066c3`
- name: `ClasspWriteUpperLevelIOFailureEvent`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005560`

## callees

- `0x140004ed0`
- `0x140006300`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoGetPagingIoPriority` at `0x1400064db`
- `ntoskrnl!IoGetPagingIoPriority` at `0x1400064db`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140006695`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140006695`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140006500`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140006500`

## pseudocode

```c
__int64 __fastcall ClasspWriteUpperLevelIOFailureEvent(int a1, __int64 a2, IRP *a3)
{
  __int64 result; // rax
  bool v6; // zf
  __int64 v7; // r11
  __int64 v8; // rbp
  __int64 v9; // rsi
  __int64 v10; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v12; // r15
  __int64 v13; // rax
  _DWORD *v14; // rcx
  __int128 *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // r9d
  int v18; // r8d
  __int64 v19; // rdx
  int v20; // r8d
  __int64 v21; // rdx
  int v22; // r8d
  __int64 v23; // rdx
  char *v24; // r8
  int v25; // ecx
  unsigned int Length; // r12d
  __int64 v27; // rdi
  char v28; // si
  char PagingIoPriority; // r14
  int v30; // ecx
  __int64 *v31; // rdx
  char IoPriorityHint; // [rsp+70h] [rbp-88h]
  int v33; // [rsp+74h] [rbp-84h] BYREF
  __int64 v34; // [rsp+78h] [rbp-80h]
  __int64 v35; // [rsp+80h] [rbp-78h]
  __int64 v36; // [rsp+88h] [rbp-70h]
  __int128 *v37; // [rsp+90h] [rbp-68h]
  _IO_STACK_LOCATION *v38; // [rsp+98h] [rbp-60h]
  __int128 v39; // [rsp+A0h] [rbp-58h] BYREF

  result = (unsigned int)a3->IoStatus.Status;
  v39 = 0;
  if ( (_DWORD)result != -1073741306 )
  {
    if ( (int)result > -1073741808 )
    {
      if ( (_DWORD)result == -1073741789 || (_DWORD)result == -1073741637 )
        return result;
      v6 = (_DWORD)result == -1073740701;
    }
    else
    {
      if ( (_DWORD)result == -1073741808 || (_DWORD)result == -2147483643 || (_DWORD)result == -1073741822 )
        return result;
      v6 = (_DWORD)result == -1073741820;
    }
    if ( v6 )
      return result;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
    v12 = *(_QWORD *)(a2 + 64);
    v38 = CurrentStackLocation;
    v36 = 0;
    v35 = 0;
    v13 = *(_QWORD *)(v12 + 1168);
    v14 = *(_DWORD **)(v12 + 520);
    v34 = 0;
    if ( v13 )
      v15 = (__int128 *)(v13 + 4);
    else
      v15 = &v39;
    v37 = v15;
    if ( v14 )
    {
      v16 = (unsigned int)v14[3];
      v17 = v14[1];
      if ( (_DWORD *)((char *)v14 + v16) < v14 )
      {
        v18 = 0;
      }
      else
      {
        v18 = v17 - v16;
        if ( (unsigned int)v16 > v17 )
          v18 = 0;
      }
      if ( (_DWORD)v16 )
      {
        if ( v18 )
          v7 = (__int64)v14 + v16;
        v36 = v7;
      }
      v19 = (unsigned int)v14[4];
      if ( (_DWORD *)((char *)v14 + v19) < v14 )
      {
        v20 = 0;
      }
      else
      {
        v20 = v17 - v19;
        if ( (unsigned int)v19 > v17 )
          v20 = 0;
      }
      if ( (_DWORD)v19 )
      {
        if ( v20 )
          v10 = (__int64)v14 + v19;
        v35 = v10;
      }
      v21 = (unsigned int)v14[5];
      if ( (_DWORD *)((char *)v14 + v21) < v14 )
      {
        v22 = 0;
      }
      else
      {
        v22 = v17 - v21;
        if ( (unsigned int)v21 > v17 )
          v22 = 0;
      }
      if ( (_DWORD)v21 )
      {
        if ( v22 )
          v9 = (__int64)v14 + v21;
        v34 = v9;
      }
      v23 = (unsigned int)v14[6];
      v24 = (char *)v14 + v23;
      if ( (_DWORD *)((char *)v14 + v23) < v14 )
      {
        v25 = 0;
      }
      else
      {
        v25 = v17 - v23;
        if ( (unsigned int)v23 > v17 )
          v25 = 0;
      }
      if ( (_DWORD)v23 && v25 )
        v8 = (__int64)v24;
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    v27 = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart >> *(_BYTE *)(v12 + 642);
    if ( (a3->Flags & 0x42) != 0 )
    {
      IoPriorityHint = 5;
      v28 = 1;
      PagingIoPriority = IoGetPagingIoPriority(a3);
    }
    else
    {
      PagingIoPriority = 0;
      v28 = 0;
      IoPriorityHint = IoGetIoPriorityHint(a3);
    }
    v33 = 0;
    if ( (int)IoGetGenericIrpExtension(a3, &v33, 4) >= 0 && (v30 = v33, (v33 & 0x10) != 0) )
      LOBYTE(v30) = v33 & 0xF;
    else
      LOBYTE(v30) = -1;
    result = (__int64)v38;
    if ( v38->MajorFunction != 3 )
    {
      if ( v28 )
      {
        if ( (BYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) != 0 )
          return McTemplateK0jqssssdixuq_EtwWriteTransfer(
                   v30,
                   (unsigned int)EventUpperLevelPagingWriteFailure,
                   a1,
                   (_DWORD)v37,
                   *(_DWORD *)(v12 + 588),
                   v36,
                   v35,
                   v34,
                   v8,
                   a3->IoStatus.Status,
                   v27,
                   Length,
                   v30,
                   PagingIoPriority);
        return result;
      }
      if ( (BYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) == 0 )
        return result;
      v31 = EventUpperLevelWriteFailure;
      return McTemplateK0jqssssdixuq_EtwWriteTransfer(
               v30,
               (_DWORD)v31,
               a1,
               (_DWORD)v37,
               *(_DWORD *)(v12 + 588),
               v36,
               v35,
               v34,
               v8,
               a3->IoStatus.Status,
               v27,
               Length,
               v30,
               IoPriorityHint);
    }
    if ( !v28 )
    {
      if ( (BYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 8) == 0 )
        return result;
      v31 = EventUpperLevelReadFailure;
      return McTemplateK0jqssssdixuq_EtwWriteTransfer(
               v30,
               (_DWORD)v31,
               a1,
               (_DWORD)v37,
               *(_DWORD *)(v12 + 588),
               v36,
               v35,
               v34,
               v8,
               a3->IoStatus.Status,
               v27,
               Length,
               v30,
               IoPriorityHint);
    }
    if ( (BYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x20) != 0 )
      return McTemplateK0jqssssdixuq_EtwWriteTransfer(
               v30,
               (unsigned int)EventUpperLevelPagingReadFailure,
               a1,
               (_DWORD)v37,
               *(_DWORD *)(v12 + 588),
               v36,
               v35,
               v34,
               v8,
               a3->IoStatus.Status,
               v27,
               Length,
               v30,
               PagingIoPriority);
  }
  return result;
}

```

## disassembly

```asm
0x140006300  push    rbx
0x140006302  push    r13
0x140006304  sub     rsp, 0E8h
0x14000630b  mov     rax, cs:__security_cookie
0x140006312  xor     rax, rsp
0x140006315  mov     [rsp+0F8h+var_48], rax
0x14000631d  mov     eax, [r8+30h]
0x140006321  xorps   xmm0, xmm0
0x140006324  mov     rbx, r8
0x140006327  mov     r13, rcx
0x14000632a  movups  [rsp+0F8h+var_58], xmm0
0x140006332  cmp     eax, 0C0000206h
0x140006337  jz      loc_1400065CE
0x14000633d  cmp     eax, 0C0000010h
0x140006342  jg      loc_1400065EA
0x140006348  jz      loc_1400065CE
0x14000634e  cmp     eax, 80000005h
0x140006353  jz      loc_1400065CE
0x140006359  cmp     eax, 0C0000002h
0x14000635e  jz      loc_1400065CE
0x140006364  cmp     eax, 0C0000004h
0x140006369  jz      loc_1400065CE
0x14000636f  mov     [rsp+0F8h+arg_18], rbp
0x140006377  xor     r11d, r11d
0x14000637a  mov     [rsp+0F8h+var_18], rsi
0x140006382  xor     ebp, ebp
0x140006384  mov     [rsp+0F8h+var_20], rdi
0x14000638c  xor     esi, esi
0x14000638e  mov     [rsp+0F8h+var_28], r12
0x140006396  xor     edi, edi
0x140006398  mov     [rsp+0F8h+var_30], r14
0x1400063a0  mov     r14, [r8+0B8h]
0x1400063a7  mov     [rsp+0F8h+var_38], r15
0x1400063af  mov     r15, [rdx+40h]
0x1400063b3  mov     [rsp+0F8h+var_60], r14
0x1400063bb  mov     [rsp+0F8h+var_70], r11
0x1400063c3  mov     [rsp+0F8h+var_78], rdi
0x1400063cb  mov     rax, [r15+490h]
0x1400063d2  mov     rcx, [r15+208h]
0x1400063d9  mov     [rsp+0F8h+var_80], rsi
0x1400063de  test    rax, rax
0x1400063e1  jz      loc_140006663
0x1400063e7  add     rax, 4
0x1400063eb  mov     [rsp+0F8h+var_68], rax
0x1400063f3  test    rcx, rcx
0x1400063f6  jz      loc_1400064AF
0x1400063fc  mov     edx, [rcx+0Ch]
0x1400063ff  mov     r9d, [rcx+4]
0x140006403  lea     r10, [rdx+rcx]
0x140006407  cmp     r10, rcx
0x14000640a  jb      loc_140006670
0x140006410  xor     eax, eax
0x140006412  mov     r8d, r9d
0x140006415  sub     r8d, edx
0x140006418  cmp     edx, r9d
0x14000641b  cmova   r8d, eax
0x14000641f  test    edx, edx
0x140006421  jnz     loc_140006617
0x140006427  mov     edx, [rcx+10h]
0x14000642a  lea     r10, [rdx+rcx]
0x14000642e  cmp     r10, rcx
0x140006431  jb      loc_140006678
0x140006437  xor     eax, eax
0x140006439  mov     r8d, r9d
0x14000643c  sub     r8d, edx
0x14000643f  cmp     edx, r9d
0x140006442  cmova   r8d, eax
0x140006446  test    edx, edx
0x140006448  jz      short loc_140006459
0x14000644a  test    r8d, r8d
0x14000644d  cmovnz  rdi, r10
0x140006451  mov     [rsp+0F8h+var_78], rdi
0x140006459  mov     edx, [rcx+14h]
0x14000645c  lea     r10, [rdx+rcx]
0x140006460  cmp     r10, rcx
0x140006463  jb      loc_140006680
0x140006469  xor     eax, eax
0x14000646b  mov     r8d, r9d
0x14000646e  sub     r8d, edx
0x140006471  cmp     edx, r9d
0x140006474  cmova   r8d, eax
0x140006478  test    edx, edx
0x14000647a  jz      short loc_140006488
0x14000647c  test    r8d, r8d
0x14000647f  cmovnz  rsi, r10
0x140006483  mov     [rsp+0F8h+var_80], rsi
0x140006488  mov     edx, [rcx+18h]
0x14000648b  lea     r8, [rdx+rcx]
0x14000648f  cmp     r8, rcx
0x140006492  jb      loc_140006688
0x140006498  xor     eax, eax
0x14000649a  mov     ecx, r9d
0x14000649d  sub     ecx, edx
0x14000649f  cmp     edx, r9d
0x1400064a2  cmova   ecx, eax
0x1400064a5  test    edx, edx
0x1400064a7  jz      short loc_1400064AF
0x1400064a9  test    ecx, ecx
0x1400064ab  cmovnz  rbp, r8
0x1400064af  movzx   ecx, byte ptr [r15+282h]
0x1400064b7  mov     rdi, [r14+18h]
0x1400064bb  mov     eax, [rbx+10h]
0x1400064be  mov     r12d, [r14+8]
0x1400064c2  sar     rdi, cl
0x1400064c5  mov     rcx, rbx; Irp
0x1400064c8  test    al, 42h
0x1400064ca  jz      loc_14000668F
0x1400064d0  mov     [rsp+0F8h+var_88], 5
0x1400064d8  mov     sil, 1
0x1400064db  call    cs:__imp_IoGetPagingIoPriority
0x1400064e2  nop     dword ptr [rax+rax+00h]
0x1400064e7  mov     r14d, eax
0x1400064ea  mov     r8d, 4
0x1400064f0  mov     [rsp+0F8h+var_84], 0
0x1400064f8  lea     rdx, [rsp+0F8h+var_84]
0x1400064fd  mov     rcx, rbx
0x140006500  call    cs:__imp_IoGetGenericIrpExtension
0x140006507  nop     dword ptr [rax+rax+00h]
0x14000650c  test    eax, eax
0x14000650e  jns     loc_14000664E
0x140006514  mov     cl, 0FFh
0x140006516  mov     rax, [rsp+0F8h+var_60]
0x14000651e  cmp     byte ptr [rax], 3
0x140006521  jz      loc_14000662B
0x140006527  test    sil, sil
0x14000652a  jz      loc_140006602
0x140006530  test    byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 40h
0x140006537  jz      short loc_14000659E
0x140006539  mov     [rsp+0F8h+var_90], r14d
0x14000653e  lea     rdx, EventUpperLevelPagingWriteFailure
0x140006545  mov     eax, [rbx+30h]
0x140006548  mov     r8, r13
0x14000654b  mov     r9, [rsp+0F8h+var_68]
0x140006553  mov     [rsp+0F8h+var_98], cl
0x140006557  mov     [rsp+0F8h+var_A0], r12
0x14000655c  mov     [rsp+0F8h+var_A8], rdi
0x140006561  mov     [rsp+0F8h+var_B0], eax
0x140006565  mov     rax, [rsp+0F8h+var_80]
0x14000656a  mov     [rsp+0F8h+var_B8], rbp
0x14000656f  mov     [rsp+0F8h+var_C0], rax
0x140006574  mov     rax, [rsp+0F8h+var_78]
0x14000657c  mov     [rsp+0F8h+var_C8], rax
0x140006581  mov     rax, [rsp+0F8h+var_70]
0x140006589  mov     [rsp+0F8h+var_D0], rax
0x14000658e  mov     eax, [r15+24Ch]
0x140006595  mov     [rsp+0F8h+var_D8], eax
0x140006599  call    McTemplateK0jqssssdixuq_EtwWriteTransfer
0x14000659e  mov     r14, [rsp+0F8h+var_30]
0x1400065a6  mov     r12, [rsp+0F8h+var_28]
0x1400065ae  mov     rdi, [rsp+0F8h+var_20]
0x1400065b6  mov     rsi, [rsp+0F8h+var_18]
0x1400065be  mov     rbp, [rsp+0F8h+arg_18]
0x1400065c6  mov     r15, [rsp+0F8h+var_38]
0x1400065ce  mov     rcx, [rsp+0F8h+var_48]
0x1400065d6  xor     rcx, rsp; StackCookie
0x1400065d9  call    __security_check_cookie
0x1400065de  add     rsp, 0E8h
0x1400065e5  pop     r13
0x1400065e7  pop     rbx
0x1400065e8  retn
0x1400065ea  cmp     eax, 0C0000023h
0x1400065ef  jz      short loc_1400065CE
0x1400065f1  cmp     eax, 0C00000BBh
0x1400065f6  jz      short loc_1400065CE
0x1400065f8  cmp     eax, 0C0000463h
0x1400065fd  jmp     loc_140006369
0x140006602  test    byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 10h
0x140006609  jz      short loc_14000659E
0x14000660b  lea     rdx, EventUpperLevelWriteFailure
0x140006612  jmp     loc_14003F078
0x140006617  test    r8d, r8d
0x14000661a  cmovnz  r11, r10
0x14000661e  mov     [rsp+0F8h+var_70], r11
0x140006626  jmp     loc_140006427
0x14000662b  test    sil, sil
0x14000662e  jz      short loc_1400066AA
0x140006630  test    byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 20h
0x140006637  jz      loc_14000659E
0x14000663d  mov     [rsp+0F8h+var_90], r14d
0x140006642  lea     rdx, EventUpperLevelPagingReadFailure
0x140006649  jmp     loc_140006545
0x14000664e  mov     ecx, [rsp+0F8h+var_84]
0x140006652  test    cl, 10h
0x140006655  jz      loc_140006514
0x14000665b  and     cl, 0Fh
0x14000665e  jmp     loc_140006516
0x140006663  lea     rax, [rsp+0F8h+var_58]
0x14000666b  jmp     loc_1400063EB
0x140006670  xor     r8d, r8d
0x140006673  jmp     loc_14000641F
0x140006678  xor     r8d, r8d
0x14000667b  jmp     loc_140006446
0x140006680  xor     r8d, r8d
0x140006683  jmp     loc_140006478
0x140006688  xor     ecx, ecx
0x14000668a  jmp     loc_1400064A5
0x14000668f  xor     r14d, r14d
0x140006692  xor     sil, sil
0x140006695  call    cs:__imp_IoGetIoPriorityHint
0x14000669c  nop     dword ptr [rax+rax+00h]
0x1400066a1  mov     [rsp+0F8h+var_88], eax
0x1400066a5  jmp     loc_1400064EA
0x1400066aa  test    byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 8
0x1400066b1  jz      loc_14000659E
0x1400066b7  lea     rdx, EventUpperLevelReadFailure
0x1400066be  jmp     loc_14003F078
0x14003f078  mov     eax, [rsp+0F8h+var_88]
0x14003f07c  mov     [rsp+0F8h+var_90], eax
0x14003f080  jmp     loc_140006545
```
