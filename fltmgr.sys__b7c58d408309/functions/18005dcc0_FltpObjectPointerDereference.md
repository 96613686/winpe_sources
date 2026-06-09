# FltpObjectPointerDereference

- ea: `0x18005dcc0`
- end: `0x18005df3c`
- name: `FltpObjectPointerDereference`
- size: `636`
- prototype: `void __fastcall(char *)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e5e0`
- `0x18000f9d0`
- `0x180010ab0`
- `0x180010f30`
- `0x1800117c0`
- `0x1800123e0`
- `0x18004c810`
- `0x18004d410`
- `0x18004eac0`
- `0x18004eb7c`
- `0x18004f410`
- `0x18004fca0`
- `0x1800543c0`
- `0x18005cfe0`
- `0x18005dc10`
- `0x18005dcc0`
- `0x18005f850`
- `0x180060e10`
- `0x180062ba0`
- `0x180063b40`
- `0x180068e20`
- `0x180070b30`

## callees

- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005ddc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005df27`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005ddc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005df27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005dd1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005de17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005debc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005dd1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005de17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005debc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005dd87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005de85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005dd87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005de85`
- `ntoskrnl!ExReleaseFastResource` at `0x18005dd7b`
- `ntoskrnl!ExReleaseFastResource` at `0x18005de79`
- `ntoskrnl!ExReleaseFastResource` at `0x18005dd7b`
- `ntoskrnl!ExReleaseFastResource` at `0x18005de79`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18005dda2`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18005dda2`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18005dd35`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18005de2f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18005ded1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18005dd35`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18005de2f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18005ded1`
- `ntoskrnl!ExDeleteFastResource` at `0x18005ddfe`
- `ntoskrnl!ExDeleteFastResource` at `0x18005ddfe`

## pseudocode

```c
void __fastcall FltpObjectPointerDereference(char *a1)
{
  int v2; // eax
  __int64 v3; // rbp
  _QWORD *v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r8
  _QWORD *v7; // rdx
  void *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // r8
  char *v11; // rcx
  __int64 v12; // r8
  char **v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  char **v16; // rdx
  _QWORD *v17; // rdi
  __int64 v18; // r8
  __int64 v19; // rcx
  _QWORD *v20; // rdx
  __int64 v21; // rsi

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 1, 0xFFFFFFFF) != 1 )
    return;
  v2 = *(_DWORD *)a1 & 0x7000000;
  switch ( v2 )
  {
    case 0x1000000:
      if ( !*((_QWORD *)a1 + 2) )
      {
LABEL_7:
        ExCleanupAutoExpandPushLock(a1 + 136);
        break;
      }
      v3 = *((_QWORD *)a1 + 8);
      v4 = a1 + 16;
      KeEnterCriticalRegion();
      LOBYTE(v5) = 1;
      ExAcquireFastResourceExclusive(v3 + 192, 0, v5);
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 312));
      v6 = *v4;
      v7 = (_QWORD *)v4[1];
      if ( *(_QWORD **)(*v4 + 8LL) == v4 && (_QWORD *)*v7 == v4 )
      {
        *v7 = v6;
        *(_QWORD *)(v6 + 8) = v7;
        *v4 = 0;
        ExReleaseFastResource(v3 + 192, 0);
        KeLeaveCriticalRegion();
        FltpObjectPointerDereference(v3);
        goto LABEL_7;
      }
LABEL_23:
      __fastfail(3u);
    case 0x2000000:
      v21 = *((_QWORD *)a1 + 7);
      if ( !*((_QWORD *)a1 + 2) )
        break;
      v17 = a1 + 16;
      KeEnterCriticalRegion();
      LOBYTE(v18) = 1;
      ExAcquireFastResourceExclusive(v21 + 72, 0, v18);
      _InterlockedDecrement((volatile signed __int32 *)(v21 + 192));
      v19 = *v17;
      v20 = (_QWORD *)v17[1];
      if ( *(_QWORD **)(*v17 + 8LL) != v17 || (_QWORD *)*v20 != v17 )
        goto LABEL_23;
      *v20 = v19;
      *(_QWORD *)(v19 + 8) = v20;
      v14 = v21 + 72;
      *v17 = 0;
LABEL_19:
      ExReleaseFastResource(v14, 0);
      KeLeaveCriticalRegion();
      break;
    case 0x4000000:
      ExDeleteFastResource(a1 + 192);
      if ( *((_QWORD *)a1 + 2) )
      {
        v9 = *((_QWORD *)a1 + 13);
        KeEnterCriticalRegion();
        LOBYTE(v10) = 1;
        ExAcquireFastResourceExclusive(v9 + 200, 0, v10);
        v11 = a1 + 16;
        if ( (*((_DWORD *)a1 + 14) & 8) != 0 )
        {
          v15 = *(_QWORD *)v11;
          if ( *(char **)(*(_QWORD *)v11 + 8LL) != v11 )
            goto LABEL_23;
          v16 = (char **)*((_QWORD *)a1 + 3);
          if ( *v16 != v11 )
            goto LABEL_23;
          *v16 = (char *)v15;
          *(_QWORD *)(v15 + 8) = v16;
        }
        else
        {
          _InterlockedDecrement((volatile signed __int32 *)(v9 + 320));
          v12 = *(_QWORD *)v11;
          v13 = (char **)*((_QWORD *)a1 + 3);
          if ( *(char **)(*(_QWORD *)v11 + 8LL) != v11 || *v13 != v11 )
            goto LABEL_23;
          *v13 = (char *)v12;
          *(_QWORD *)(v12 + 8) = v13;
        }
        *((_QWORD *)a1 + 2) = 0;
        v14 = v9 + 200;
        goto LABEL_19;
      }
      break;
  }
  v8 = (void *)*((_QWORD *)a1 + 4);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0x6C724D46u);
    *((_QWORD *)a1 + 4) = 0;
  }
  ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x18005dcc0  push    rbx
0x18005dcc2  sub     rsp, 20h
0x18005dcc6  mov     rbx, rcx
0x18005dcc9  mov     eax, 0FFFFFFFFh
0x18005dcce  lock xadd [rcx+4], eax
0x18005dcd3  cmp     eax, 1
0x18005dcd6  jz      short loc_18005DCDF
0x18005dcd8  add     rsp, 20h
0x18005dcdc  pop     rbx
0x18005dcdd  retn
0x18005dcdf  mov     eax, [rcx]
0x18005dce1  mov     [rsp+28h+arg_18], r14
0x18005dce6  and     eax, 7000000h
0x18005dceb  mov     [rsp+28h+arg_0], rbp
0x18005dcf0  xor     r14d, r14d
0x18005dcf3  mov     [rsp+28h+arg_8], rsi
0x18005dcf8  mov     [rsp+28h+arg_10], rdi
0x18005dcfd  cmp     eax, 1000000h
0x18005dd02  jnz     loc_18005DDE5
0x18005dd08  mov     rax, [rcx+10h]
0x18005dd0c  test    rax, rax
0x18005dd0f  jz      loc_18005DD9B
0x18005dd15  mov     rbp, [rcx+40h]
0x18005dd19  lea     rdi, [rcx+10h]
0x18005dd1d  call    cs:__imp_KeEnterCriticalRegion
0x18005dd24  nop     dword ptr [rax+rax+00h]
0x18005dd29  mov     r8b, 1
0x18005dd2c  lea     rcx, [rbp+0C0h]
0x18005dd33  xor     edx, edx
0x18005dd35  call    cs:__imp_ExAcquireFastResourceExclusive
0x18005dd3c  nop     dword ptr [rax+rax+00h]
0x18005dd41  lock dec dword ptr [rbp+138h]
0x18005dd48  mov     r8, [rdi]
0x18005dd4b  mov     rdx, [rdi+8]
0x18005dd4f  mov     rax, [r8+8]
0x18005dd53  cmp     rax, rdi
0x18005dd56  jnz     loc_18005DEB1
0x18005dd5c  mov     rax, [rdx]
0x18005dd5f  cmp     rax, rdi
0x18005dd62  jnz     loc_18005DEB1
0x18005dd68  mov     [rdx], r8
0x18005dd6b  lea     rcx, [rbp+0C0h]
0x18005dd72  mov     [r8+8], rdx
0x18005dd76  xor     edx, edx
0x18005dd78  mov     [rdi], r14
0x18005dd7b  call    cs:__imp_ExReleaseFastResource
0x18005dd82  nop     dword ptr [rax+rax+00h]
0x18005dd87  call    cs:__imp_KeLeaveCriticalRegion
0x18005dd8e  nop     dword ptr [rax+rax+00h]
0x18005dd93  mov     rcx, rbp
0x18005dd96  call    FltpObjectPointerDereference
0x18005dd9b  lea     rcx, [rbx+88h]
0x18005dda2  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18005dda9  nop     dword ptr [rax+rax+00h]
0x18005ddae  mov     rcx, [rbx+20h]; P
0x18005ddb2  test    rcx, rcx
0x18005ddb5  jnz     loc_18005DF22
0x18005ddbb  xor     edx, edx; Tag
0x18005ddbd  mov     rcx, rbx; P
0x18005ddc0  call    cs:__imp_ExFreePoolWithTag
0x18005ddc7  nop     dword ptr [rax+rax+00h]
0x18005ddcc  mov     rdi, [rsp+28h+arg_10]
0x18005ddd1  mov     rsi, [rsp+28h+arg_8]
0x18005ddd6  mov     rbp, [rsp+28h+arg_0]
0x18005dddb  mov     r14, [rsp+28h+arg_18]
0x18005dde0  jmp     loc_18005DCD8
0x18005dde5  cmp     eax, 2000000h
0x18005ddea  jz      loc_18005DF0F
0x18005ddf0  cmp     eax, 4000000h
0x18005ddf5  jnz     short loc_18005DDAE
0x18005ddf7  add     rcx, 0C0h
0x18005ddfe  call    cs:__imp_ExDeleteFastResource
0x18005de05  nop     dword ptr [rax+rax+00h]
0x18005de0a  mov     rax, [rbx+10h]
0x18005de0e  test    rax, rax
0x18005de11  jz      short loc_18005DDAE
0x18005de13  mov     rdi, [rbx+68h]
0x18005de17  call    cs:__imp_KeEnterCriticalRegion
0x18005de1e  nop     dword ptr [rax+rax+00h]
0x18005de23  mov     r8b, 1
0x18005de26  lea     rcx, [rdi+0C8h]
0x18005de2d  xor     edx, edx
0x18005de2f  call    cs:__imp_ExAcquireFastResourceExclusive
0x18005de36  nop     dword ptr [rax+rax+00h]
0x18005de3b  mov     eax, [rbx+38h]
0x18005de3e  lea     rcx, [rbx+10h]
0x18005de42  test    al, 8
0x18005de44  jnz     short loc_18005DE96
0x18005de46  lock dec dword ptr [rdi+140h]
0x18005de4d  mov     r8, [rcx]
0x18005de50  mov     rdx, [rcx+8]
0x18005de54  mov     rax, [r8+8]
0x18005de58  cmp     rax, rcx
0x18005de5b  jnz     short loc_18005DEB1
0x18005de5d  mov     rax, [rdx]
0x18005de60  cmp     rax, rcx
0x18005de63  jnz     short loc_18005DEB1
0x18005de65  mov     [rdx], r8
0x18005de68  mov     [r8+8], rdx
0x18005de6c  mov     [rbx+10h], r14
0x18005de70  lea     rcx, [rdi+0C8h]
0x18005de77  xor     edx, edx
0x18005de79  call    cs:__imp_ExReleaseFastResource
0x18005de80  nop     dword ptr [rax+rax+00h]
0x18005de85  call    cs:__imp_KeLeaveCriticalRegion
0x18005de8c  nop     dword ptr [rax+rax+00h]
0x18005de91  jmp     loc_18005DDAE
0x18005de96  mov     rax, [rcx]
0x18005de99  cmp     [rax+8], rcx
0x18005de9d  jnz     short loc_18005DEB1
0x18005de9f  mov     rdx, [rcx+8]
0x18005dea3  cmp     [rdx], rcx
0x18005dea6  jnz     short loc_18005DEB1
0x18005dea8  mov     [rdx], rax
0x18005deab  mov     [rax+8], rdx
0x18005deaf  jmp     short loc_18005DE6C
0x18005deb1  mov     ecx, 3
0x18005deb6  int     29h; Win8: RtlFailFast(ecx)
0x18005deb8  lea     rdi, [rcx+10h]
0x18005debc  call    cs:__imp_KeEnterCriticalRegion
0x18005dec3  nop     dword ptr [rax+rax+00h]
0x18005dec8  mov     r8b, 1
0x18005decb  lea     rcx, [rsi+48h]
0x18005decf  xor     edx, edx
0x18005ded1  call    cs:__imp_ExAcquireFastResourceExclusive
0x18005ded8  nop     dword ptr [rax+rax+00h]
0x18005dedd  lock dec dword ptr [rsi+0C0h]
0x18005dee4  mov     rcx, [rdi]
0x18005dee7  mov     rdx, [rdi+8]
0x18005deeb  mov     rax, [rcx+8]
0x18005deef  cmp     rax, rdi
0x18005def2  jnz     short loc_18005DEB1
0x18005def4  mov     rax, [rdx]
0x18005def7  cmp     rax, rdi
0x18005defa  jnz     short loc_18005DEB1
0x18005defc  mov     [rdx], rcx
0x18005deff  mov     [rcx+8], rdx
0x18005df03  lea     rcx, [rsi+48h]
0x18005df07  mov     [rdi], r14
0x18005df0a  jmp     loc_18005DE77
0x18005df0f  mov     rax, [rcx+10h]
0x18005df13  mov     rsi, [rcx+38h]
0x18005df17  test    rax, rax
0x18005df1a  jz      loc_18005DDAE
0x18005df20  jmp     short loc_18005DEB8
0x18005df22  mov     edx, 6C724D46h; Tag
0x18005df27  call    cs:__imp_ExFreePoolWithTag
0x18005df2e  nop     dword ptr [rax+rax+00h]
0x18005df33  mov     [rbx+20h], r14
0x18005df37  jmp     loc_18005DDBB
```
