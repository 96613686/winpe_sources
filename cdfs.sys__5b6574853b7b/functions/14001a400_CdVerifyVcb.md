# CdVerifyVcb

- ea: `0x14001a400`
- end: `0x14001a680`
- name: `CdVerifyVcb`
- size: `640`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c8b4`
- `0x14000e844`
- `0x140011674`
- `0x1400141e0`
- `0x140014e4c`
- `0x14001a688`

## callees

- `0x140001114`
- `0x14000287c`
- `0x14000fcf8`
- `0x14001a400`

## import_xrefs

- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a5da`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a62f`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a5da`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a62f`

## pseudocode

```c
char __fastcall CdVerifyVcb(__int64 a1, __int64 a2)
{
  int v3; // edx
  NTSTATUS v5; // esi
  char v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rax
  bool v9; // bl
  int v10; // ecx
  int v12; // [rsp+88h] [rbp+10h] BYREF

  v12 = 0;
  v3 = *(_DWORD *)(a2 + 52);
  if ( v3 == 3 || v3 == 4 && *(_BYTE *)(a1 + 64) )
  {
    if ( (*(_DWORD *)(a2 + 48) & 0x800) != 0 )
      CdRaiseStatusEx(a1, -1073741202, 0, 1769472, 463);
    CdRaiseStatusEx(a1, -1073741672, 0, 1769472, 467);
  }
  v5 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 16LL);
  LODWORD(v8) = *(_DWORD *)(a2 + 48);
  v9 = (*(_DWORD *)(v7 + 48) & 2) != 0;
  if ( (v8 & 0x20) == 0 || (*(_DWORD *)(v7 + 48) & 2) != 0 )
  {
LABEL_17:
    if ( !v9 && v5 >= 0 )
      goto LABEL_19;
LABEL_33:
    IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), *(PDEVICE_OBJECT *)(*(_QWORD *)(a2 + 8) + 16LL));
    if ( v6 || v9 )
      v5 = -2147483626;
    CdRaiseStatusEx(a1, v5, 0, 1769472, 585);
  }
  if ( v3 != 1 )
  {
    v5 = CdPerformDevIoCtrlEx(v7, 149504, *(_QWORD *)(a2 + 16), 0, 0, &v12, 4);
    LOBYTE(v8) = 0;
    v12 = 0;
    if ( *(_DWORD *)(a2 + 52) == 2 && (v5 == -1073741661 || v5 == -1073741805) )
      goto LABEL_13;
    if ( v5 == -2147483626 )
      goto LABEL_13;
    if ( v5 < 0 )
    {
LABEL_16:
      if ( v6 )
        goto LABEL_33;
      goto LABEL_17;
    }
    if ( *(_DWORD *)(a2 + 544) )
    {
LABEL_13:
      if ( (*(_DWORD *)(a2 + 48) & 0x200) == 0 )
      {
        LOBYTE(v8) = CdMarkDevForVerifyIfVcbMounted(a2);
        v9 = v8;
      }
      v6 = 1;
      if ( v5 >= 0 )
        goto LABEL_33;
      goto LABEL_16;
    }
  }
  if ( v9 )
    goto LABEL_33;
  if ( !*(_BYTE *)(a1 + 64) )
  {
    v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL) + 48LL);
    if ( !*(_QWORD *)(v8 + 64) && (*(_DWORD *)(a2 + 52) & 0xFFFFFFFB) == 0 )
    {
      v6 = 1;
      goto LABEL_33;
    }
  }
LABEL_19:
  v10 = *(_DWORD *)(a2 + 52);
  if ( !v10 )
  {
    IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), *(PDEVICE_OBJECT *)(*(_QWORD *)(a2 + 8) + 16LL));
    CdRaiseStatusEx(a1, -1073741806, 0, 1769472, 599);
  }
  if ( (unsigned int)(v10 - 3) <= 1 )
  {
    if ( (*(_DWORD *)(a2 + 48) & 0x800) == 0 )
      CdRaiseStatusEx(a1, -1073741672, 0, 1769472, 611);
    CdRaiseStatusEx(a1, -1073741202, 0, 1769472, 607);
  }
  return v8;
}

```

## disassembly

```asm
0x14001a400  mov     rax, rsp
0x14001a403  mov     [rax+8], rbx
0x14001a407  mov     [rax+18h], rbp
0x14001a40b  push    rsi
0x14001a40c  push    rdi
0x14001a40d  push    r14
0x14001a40f  sub     rsp, 60h
0x14001a413  mov     rdi, rdx
0x14001a416  mov     dword ptr [rax+10h], 0
0x14001a41d  mov     edx, [rdx+34h]
0x14001a420  xorps   xmm0, xmm0
0x14001a423  mov     rbp, rcx
0x14001a426  movups  xmmword ptr [rax-28h], xmm0
0x14001a42a  cmp     edx, 3
0x14001a42d  jz      loc_14001A587
0x14001a433  cmp     edx, 4
0x14001a436  jnz     short loc_14001A442
0x14001a438  cmp     byte ptr [rcx+40h], 0
0x14001a43c  jnz     loc_14001A587
0x14001a442  mov     rax, [rdi+8]
0x14001a446  xor     esi, esi
0x14001a448  xor     r14b, r14b
0x14001a44b  mov     rcx, [rax+10h]
0x14001a44f  mov     eax, [rdi+30h]
0x14001a452  mov     r8d, [rcx+30h]
0x14001a456  and     r8d, 2
0x14001a45a  setnz   bl
0x14001a45d  test    al, 20h
0x14001a45f  jz      loc_14001A51D
0x14001a465  test    r8d, r8d
0x14001a468  jnz     loc_14001A51D
0x14001a46e  cmp     edx, 1
0x14001a471  jz      loc_14001A55C
0x14001a477  mov     r8, [rdi+10h]
0x14001a47b  lea     rax, [rsp+78h+var_28]
0x14001a480  mov     [rsp+78h+var_30], rax
0x14001a485  xor     r9d, r9d
0x14001a488  mov     [rsp+78h+var_38], sil
0x14001a48d  lea     rax, [rsp+78h+arg_8]
0x14001a495  mov     [rsp+78h+var_48], 4
0x14001a49d  mov     edx, 24800h
0x14001a4a2  mov     [rsp+78h+var_50], rax
0x14001a4a7  mov     [rsp+78h+var_58], esi
0x14001a4ab  call    CdPerformDevIoCtrlEx
0x14001a4b0  cmp     [rsp+78h+var_20], 4
0x14001a4b6  mov     esi, eax
0x14001a4b8  jz      short loc_14001A4C5
0x14001a4ba  xor     eax, eax
0x14001a4bc  mov     [rsp+78h+arg_8], eax
0x14001a4c3  jmp     short loc_14001A4CC
0x14001a4c5  mov     eax, [rsp+78h+arg_8]
0x14001a4cc  cmp     dword ptr [rdi+34h], 2
0x14001a4d0  jnz     short loc_14001A4E2
0x14001a4d2  cmp     esi, 0C00000A3h
0x14001a4d8  jz      short loc_14001A4F6
0x14001a4da  cmp     esi, 0C0000013h
0x14001a4e0  jz      short loc_14001A4F6
0x14001a4e2  cmp     esi, 80000016h
0x14001a4e8  jz      short loc_14001A4F6
0x14001a4ea  test    esi, esi
0x14001a4ec  js      short loc_14001A514
0x14001a4ee  cmp     [rdi+220h], eax
0x14001a4f4  jz      short loc_14001A55C
0x14001a4f6  test    dword ptr [rdi+30h], 200h
0x14001a4fd  jnz     short loc_14001A509
0x14001a4ff  mov     rcx, rdi
0x14001a502  call    CdMarkDevForVerifyIfVcbMounted
0x14001a507  mov     bl, al
0x14001a509  mov     r14b, 1
0x14001a50c  test    esi, esi
0x14001a50e  jns     loc_14001A5CE
0x14001a514  test    r14b, r14b
0x14001a517  jnz     loc_14001A5CE
0x14001a51d  test    bl, bl
0x14001a51f  jnz     loc_14001A5CE
0x14001a525  test    esi, esi
0x14001a527  js      loc_14001A5CE
0x14001a52d  mov     ecx, [rdi+34h]
0x14001a530  test    ecx, ecx
0x14001a532  jz      loc_14001A623
0x14001a538  sub     ecx, 3
0x14001a53b  jz      short loc_14001A542
0x14001a53d  cmp     ecx, 1
0x14001a540  jnz     short loc_14001A5A2
0x14001a542  xor     r8d, r8d
0x14001a545  mov     r9d, 1B0000h
0x14001a54b  test    dword ptr [rdi+30h], 800h
0x14001a552  mov     rcx, rbp
0x14001a555  jnz     short loc_14001A5B8
0x14001a557  jmp     loc_14001A610
0x14001a55c  test    bl, bl
0x14001a55e  jnz     short loc_14001A5CE
0x14001a560  cmp     [rbp+40h], r14b
0x14001a564  jnz     short loc_14001A52D
0x14001a566  mov     rax, [rbp+8]
0x14001a56a  mov     rcx, [rax+0B8h]
0x14001a571  mov     rax, [rcx+30h]
0x14001a575  cmp     qword ptr [rax+40h], 0
0x14001a57a  jnz     short loc_14001A52D
0x14001a57c  test    dword ptr [rdi+34h], 0FFFFFFFBh
0x14001a583  jz      short loc_14001A5CB
0x14001a585  jmp     short loc_14001A52D
0x14001a587  xor     r8d, r8d
0x14001a58a  mov     r9d, 1B0000h
0x14001a590  test    dword ptr [rdi+30h], 800h
0x14001a597  jz      loc_14001A66D
0x14001a59d  jmp     loc_14001A65A
0x14001a5a2  lea     r11, [rsp+78h+var_18]
0x14001a5a7  mov     rbx, [r11+20h]
0x14001a5ab  mov     rbp, [r11+30h]
0x14001a5af  mov     rsp, r11
0x14001a5b2  pop     r14
0x14001a5b4  pop     rdi
0x14001a5b5  pop     rsi
0x14001a5b6  retn
0x14001a5b8  mov     edx, 0C000026Eh
0x14001a5bd  mov     [rsp+78h+var_58], 25Fh
0x14001a5c5  call    CdRaiseStatusEx
0x14001a5cb  mov     r14b, 1
0x14001a5ce  mov     rdx, [rdi+8]
0x14001a5d2  mov     rcx, [rbp+8]; Irp
0x14001a5d6  mov     rdx, [rdx+10h]; DeviceObject
0x14001a5da  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14001a5e1  nop     dword ptr [rax+rax+00h]
0x14001a5e6  test    r14b, r14b
0x14001a5e9  jnz     short loc_14001A5EF
0x14001a5eb  test    bl, bl
0x14001a5ed  jz      short loc_14001A5F4
0x14001a5ef  mov     esi, 80000016h
0x14001a5f4  mov     r9d, 1B0000h
0x14001a5fa  mov     [rsp+78h+var_58], 249h
0x14001a602  xor     r8d, r8d
0x14001a605  mov     edx, esi
0x14001a607  mov     rcx, rbp
0x14001a60a  call    CdRaiseStatusEx
0x14001a610  mov     edx, 0C0000098h
0x14001a615  mov     [rsp+78h+var_58], 263h
0x14001a61d  call    CdRaiseStatusEx
0x14001a623  mov     rdx, [rdi+8]
0x14001a627  mov     rcx, [rbp+8]; Irp
0x14001a62b  mov     rdx, [rdx+10h]; DeviceObject
0x14001a62f  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14001a636  nop     dword ptr [rax+rax+00h]
0x14001a63b  mov     r9d, 1B0000h
0x14001a641  mov     [rsp+78h+var_58], 257h
0x14001a649  xor     r8d, r8d
0x14001a64c  mov     edx, 0C0000012h
0x14001a651  mov     rcx, rbp
0x14001a654  call    CdRaiseStatusEx
0x14001a65a  mov     edx, 0C000026Eh
0x14001a65f  mov     [rsp+78h+var_58], 1CFh
0x14001a667  call    CdRaiseStatusEx
0x14001a66d  mov     edx, 0C0000098h
0x14001a672  mov     [rsp+78h+var_58], 1D3h
0x14001a67a  call    CdRaiseStatusEx
```
