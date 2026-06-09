# CIISComputer::BackupWithPassword(ushort *,long,long,ushort *)

- ea: `0x180006790`
- end: `0x180006834`
- name: `?BackupWithPassword@CIISComputer@@UEAAJPEAGJJ0@Z`
- size: `164`
- prototype: `__int64 __fastcall(CIISComputer *this, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006790`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::BackupWithPassword(
        CIISComputer *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v8; // rdi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  int v10; // ebx
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v8 = a5;
  if ( !a5 )
    return 2147500035LL;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 15);
  v12 = 0;
  v10 = (**v9)(v9, &IID_IMSAdminBase2_W, &v12);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)v12 + 272LL))(
            v12,
            a2,
            a3,
            a4,
            v8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006790  mov     r11, rsp
0x180006793  mov     [r11+8], rbx
0x180006797  mov     [r11+18h], rbp
0x18000679b  push    rsi
0x18000679c  push    rdi
0x18000679d  push    r14
0x18000679f  sub     rsp, 30h
0x1800067a3  mov     ebp, r9d
0x1800067a6  mov     r14d, r8d
0x1800067a9  mov     rsi, rdx
0x1800067ac  test    rdx, rdx
0x1800067af  jz      short loc_18000681C
0x1800067b1  mov     rdi, [rsp+48h+arg_20]
0x1800067b6  test    rdi, rdi
0x1800067b9  jz      short loc_18000681C
0x1800067bb  mov     rcx, [rcx+78h]
0x1800067bf  lea     r8, [r11+10h]
0x1800067c3  mov     qword ptr [r11+10h], 0
0x1800067cb  lea     rdx, IID_IMSAdminBase2_W
0x1800067d2  mov     rax, [rcx]
0x1800067d5  mov     rax, [rax]
0x1800067d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067dd  mov     ebx, eax
0x1800067df  test    eax, eax
0x1800067e1  js      short loc_180006818
0x1800067e3  mov     rcx, [rsp+48h+arg_8]
0x1800067e8  mov     r9d, ebp
0x1800067eb  mov     r8d, r14d
0x1800067ee  mov     [rsp+48h+var_28], rdi
0x1800067f3  mov     rdx, rsi
0x1800067f6  mov     rax, [rcx]
0x1800067f9  mov     rax, [rax+110h]
0x180006800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006805  mov     rcx, [rsp+48h+arg_8]
0x18000680a  mov     ebx, eax
0x18000680c  mov     rax, [rcx]
0x18000680f  mov     rax, [rax+10h]
0x180006813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006818  mov     eax, ebx
0x18000681a  jmp     short loc_180006821
0x18000681c  mov     eax, 80004003h
0x180006821  mov     rbx, [rsp+48h+arg_0]
0x180006826  mov     rbp, [rsp+48h+arg_10]
0x18000682b  add     rsp, 30h
0x18000682f  pop     r14
0x180006831  pop     rdi
0x180006832  pop     rsi
0x180006833  retn
```
