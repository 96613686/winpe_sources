# DwmHLSurfGetDirtyRgn

- ea: `0x180047850`
- end: `0x1800479a9`
- name: `DwmHLSurfGetDirtyRgn`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180047850`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004793d`
- `GDI32!DeleteObject` at `0x180047963`
- `GDI32!DeleteObject` at `0x180047988`
- `GDI32!DeleteObject` at `0x18004793d`
- `GDI32!DeleteObject` at `0x180047963`
- `GDI32!DeleteObject` at `0x180047988`
- `win32u!NtGdiHLSurfGetInformation` at `0x1800478a5`
- `win32u!NtGdiHLSurfGetInformation` at `0x1800478a5`

## pseudocode

```c
__int64 __fastcall DwmHLSurfGetDirtyRgn(
        __int64 a1,
        void *a2,
        HGDIOBJ *a3,
        HGDIOBJ *a4,
        HGDIOBJ *a5,
        _QWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        _DWORD *a9)
{
  _QWORD *v9; // rbx
  unsigned int v12; // r14d
  _DWORD *v13; // rcx
  HGDIOBJ ho[2]; // [rsp+20h] [rbp-40h] BYREF
  HGDIOBJ v16[2]; // [rsp+30h] [rbp-30h]
  __int128 v17; // [rsp+40h] [rbp-20h]
  __int64 v18; // [rsp+50h] [rbp-10h]
  int v19; // [rsp+88h] [rbp+28h] BYREF

  v9 = a6;
  v18 = 0;
  ho[1] = 0;
  ho[0] = a2;
  v19 = 56;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v12 = ((__int64 (__fastcall *)(__int64, _QWORD, HGDIOBJ *, int *))NtGdiHLSurfGetInformation)(
          a1,
          a6 != 0 ? 9 : 4,
          ho,
          &v19);
  if ( a3 )
  {
    *a3 = ho[1];
  }
  else if ( ho[1] )
  {
    DeleteObject(ho[1]);
    ho[1] = 0;
  }
  if ( a4 )
  {
    *a4 = v16[0];
  }
  else if ( v16[0] )
  {
    DeleteObject(v16[0]);
    v16[0] = 0;
  }
  if ( a5 )
  {
    *a5 = v16[1];
  }
  else if ( v16[1] )
  {
    DeleteObject(v16[1]);
  }
  if ( v9 )
    *v9 = v17;
  v13 = a7;
  if ( a7 )
  {
    *a7 = DWORD2(v17);
    v13[1] = HIDWORD(v17);
  }
  if ( a8 )
    *a8 = v18;
  if ( a9 )
    *a9 = HIDWORD(v18);
  return v12;
}

```

## disassembly

```asm
0x180047850  mov     [rsp-18h+arg_0], rbx
0x180047855  mov     [rsp-18h+arg_10], rsi
0x18004785a  push    rbp
0x18004785b  push    rdi
0x18004785c  push    r14
0x18004785e  mov     rbp, rsp
0x180047861  sub     rsp, 60h
0x180047865  mov     rbx, [rbp+arg_28]
0x180047869  xor     eax, eax
0x18004786b  xorps   xmm0, xmm0
0x18004786e  mov     [rbp+var_10], rax
0x180047872  movups  xmmword ptr [rbp+ho], xmm0
0x180047876  mov     [rbp+ho], rdx
0x18004787a  mov     rdi, r9
0x18004787d  mov     rsi, r8
0x180047880  mov     [rbp+arg_8], 38h ; '8'
0x180047887  mov     rax, rbx
0x18004788a  lea     r9, [rbp+arg_8]
0x18004788e  neg     rax
0x180047891  lea     r8, [rbp+ho]
0x180047895  movups  xmmword ptr [rbp+var_30], xmm0
0x180047899  sbb     edx, edx
0x18004789b  and     edx, 5
0x18004789e  add     edx, 4
0x1800478a1  movups  [rbp+var_20], xmm0
0x1800478a5  call    cs:__imp_NtGdiHLSurfGetInformation
0x1800478ac  nop     dword ptr [rax+rax+00h]
0x1800478b1  mov     rcx, [rbp+ho+8]; ho
0x1800478b5  mov     r14d, eax
0x1800478b8  test    rsi, rsi
0x1800478bb  jz      short loc_180047938
0x1800478bd  mov     [rsi], rcx
0x1800478c0  test    rdi, rdi
0x1800478c3  jz      loc_180047956
0x1800478c9  mov     rax, [rbp+var_30]
0x1800478cd  mov     [rdi], rax
0x1800478d0  mov     rcx, [rbp+arg_20]
0x1800478d4  test    rcx, rcx
0x1800478d7  jnz     loc_18004797C
0x1800478dd  mov     rcx, [rbp+var_30+8]; ho
0x1800478e1  test    rcx, rcx
0x1800478e4  jnz     loc_180047988
0x1800478ea  test    rbx, rbx
0x1800478ed  jz      short loc_1800478F6
0x1800478ef  mov     rax, qword ptr [rbp+var_20]
0x1800478f3  mov     [rbx], rax
0x1800478f6  mov     rcx, [rbp+arg_30]
0x1800478fa  test    rcx, rcx
0x1800478fd  jnz     loc_180047999
0x180047903  mov     rcx, [rbp+arg_38]
0x180047907  test    rcx, rcx
0x18004790a  jz      short loc_180047911
0x18004790c  mov     eax, dword ptr [rbp+var_10]
0x18004790f  mov     [rcx], eax
0x180047911  mov     rcx, [rbp+arg_40]
0x180047915  test    rcx, rcx
0x180047918  jz      short loc_18004791F
0x18004791a  mov     eax, dword ptr [rbp+var_10+4]
0x18004791d  mov     [rcx], eax
0x18004791f  lea     r11, [rsp+60h+var_s0]
0x180047924  mov     eax, r14d
0x180047927  mov     rbx, [r11+20h]
0x18004792b  mov     rsi, [r11+30h]
0x18004792f  mov     rsp, r11
0x180047932  pop     r14
0x180047934  pop     rdi
0x180047935  pop     rbp
0x180047936  retn
0x180047938  test    rcx, rcx
0x18004793b  jz      short loc_1800478C0
0x18004793d  call    cs:__imp_DeleteObject
0x180047944  nop     dword ptr [rax+rax+00h]
0x180047949  mov     [rbp+ho+8], 0
0x180047951  jmp     loc_1800478C0
0x180047956  mov     rcx, [rbp+var_30]; ho
0x18004795a  test    rcx, rcx
0x18004795d  jz      loc_1800478D0
0x180047963  call    cs:__imp_DeleteObject
0x18004796a  nop     dword ptr [rax+rax+00h]
0x18004796f  mov     [rbp+var_30], 0
0x180047977  jmp     loc_1800478D0
0x18004797c  mov     rax, [rbp+var_30+8]
0x180047980  mov     [rcx], rax
0x180047983  jmp     loc_1800478EA
0x180047988  call    cs:__imp_DeleteObject
0x18004798f  nop     dword ptr [rax+rax+00h]
0x180047994  jmp     loc_1800478EA
0x180047999  mov     eax, dword ptr [rbp+var_20+8]
0x18004799c  mov     [rcx], eax
0x18004799e  mov     eax, dword ptr [rbp+var_20+0Ch]
0x1800479a1  mov     [rcx+4], eax
0x1800479a4  jmp     loc_180047903
```
