# MupiCreateUncHardeningConfigurationEntry

- ea: `0x140015610`
- end: `0x140015708`
- name: `MupiCreateUncHardeningConfigurationEntry`
- size: `248`
- prototype: `__int64 __fastcall(PCUNICODE_STRING StringIn)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140015750`
- `0x14001f030`

## callees

- `0x1400056c0`
- `0x1400059c0`
- `0x140015610`
- `0x140015710`
- `0x140018960`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140015670`
- `ntoskrnl!ExAllocatePool2` at `0x140015670`

## pseudocode

```c
__int64 __fastcall MupiCreateUncHardeningConfigurationEntry(PCUNICODE_STRING StringIn, __int16 *a2, _QWORD *a3)
{
  USHORT Length; // ax
  unsigned __int16 v7; // di
  int v8; // esi
  _DWORD *Pool2; // rax
  _DWORD *v10; // rbx

  if ( StringIn )
    Length = StringIn->Length;
  else
    Length = 0;
  if ( a2 )
    v7 = *a2;
  else
    v7 = 0;
  *a3 = 0;
  if ( Length || v7 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(258, v7 + 96LL, 1213560141);
    v10 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x60u);
      *v10 = 6320398;
      v10[1] = 1;
      *((_QWORD *)v10 + 2) = v10 + 2;
      *((_QWORD *)v10 + 1) = v10 + 2;
      v8 = MupInitializeServerName(StringIn);
      if ( v8 < 0 )
      {
        MupiDereferenceUncHardeningConfigurationEntry(v10);
      }
      else
      {
        if ( v7 )
        {
          *((_WORD *)v10 + 33) = v7;
          *((_QWORD *)v10 + 9) = v10 + 24;
          *((_WORD *)v10 + 32) = v7;
          memmove(v10 + 24, *((const void **)a2 + 1), v7);
        }
        *a3 = v10;
        return 0;
      }
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140015610  push    rbx
0x140015612  push    rbp
0x140015613  push    rsi
0x140015614  push    rdi
0x140015615  push    r12
0x140015617  push    r13
0x140015619  push    r14
0x14001561b  push    r15
0x14001561d  sub     rsp, 28h
0x140015621  xor     r13d, r13d
0x140015624  mov     r15, r8
0x140015627  mov     r14, rdx
0x14001562a  mov     rsi, rcx
0x14001562d  test    rcx, rcx
0x140015630  jz      short loc_140015637
0x140015632  movzx   eax, word ptr [rcx]
0x140015635  jmp     short loc_14001563A
0x140015637  mov     eax, r13d
0x14001563a  test    r14, r14
0x14001563d  jz      short loc_140015644
0x14001563f  movzx   edi, word ptr [rdx]
0x140015642  jmp     short loc_140015647
0x140015644  mov     edi, r13d
0x140015647  mov     [r8], r13
0x14001564a  test    ax, ax
0x14001564d  jnz     short loc_14001565E
0x14001564f  test    di, di
0x140015652  jnz     short loc_14001565E
0x140015654  mov     esi, 0C000000Dh
0x140015659  jmp     loc_1400156F4
0x14001565e  movzx   ebp, di
0x140015661  mov     ecx, 102h
0x140015666  mov     r8d, 4855754Dh
0x14001566c  lea     rdx, [rbp+60h]
0x140015670  call    cs:__imp_ExAllocatePool2
0x140015677  nop     dword ptr [rax+rax+00h]
0x14001567c  mov     rbx, rax
0x14001567f  test    rax, rax
0x140015682  jnz     short loc_14001568B
0x140015684  mov     esi, 0C0000017h
0x140015689  jmp     short loc_1400156F4
0x14001568b  xor     edx, edx; Val
0x14001568d  mov     rcx, rbx; void *
0x140015690  lea     r8d, [rdx+60h]; Size
0x140015694  call    memset
0x140015699  lea     rax, [rbx+8]
0x14001569d  mov     dword ptr [rbx], 60710Eh
0x1400156a3  mov     dword ptr [rbx+4], 1
0x1400156aa  lea     rdx, [rbx+18h]
0x1400156ae  mov     rcx, rsi; StringIn
0x1400156b1  mov     [rax+8], rax
0x1400156b5  mov     [rax], rax
0x1400156b8  call    MupInitializeServerName
0x1400156bd  mov     esi, eax
0x1400156bf  test    eax, eax
0x1400156c1  js      short loc_1400156EC
0x1400156c3  test    di, di
0x1400156c6  jz      short loc_1400156E4
0x1400156c8  lea     rcx, [rbx+60h]; void *
0x1400156cc  mov     [rbx+42h], di
0x1400156d0  mov     [rbx+48h], rcx
0x1400156d4  mov     r8, rbp; Size
0x1400156d7  mov     [rbx+40h], di
0x1400156db  mov     rdx, [r14+8]; Src
0x1400156df  call    memmove
0x1400156e4  mov     [r15], rbx
0x1400156e7  mov     esi, r13d
0x1400156ea  jmp     short loc_1400156F4
0x1400156ec  mov     rcx, rbx; P
0x1400156ef  call    MupiDereferenceUncHardeningConfigurationEntry
0x1400156f4  mov     eax, esi
0x1400156f6  add     rsp, 28h
0x1400156fa  pop     r15
0x1400156fc  pop     r14
0x1400156fe  pop     r13
0x140015700  pop     r12
0x140015702  pop     rdi
0x140015703  pop     rsi
0x140015704  pop     rbp
0x140015705  pop     rbx
0x140015706  retn
```
