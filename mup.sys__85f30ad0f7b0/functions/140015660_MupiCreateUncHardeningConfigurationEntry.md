# MupiCreateUncHardeningConfigurationEntry

- ea: `0x140015660`
- end: `0x140015758`
- name: `MupiCreateUncHardeningConfigurationEntry`
- size: `248`
- prototype: `__int64 __fastcall(PCUNICODE_STRING StringIn, __int16 *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400157a0`
- `0x14001f080`

## callees

- `0x1400056c0`
- `0x1400059c0`
- `0x140015660`
- `0x140015760`
- `0x1400189b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400156c0`
- `ntoskrnl!ExAllocatePool2` at `0x1400156c0`

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
0x140015660  push    rbx
0x140015662  push    rbp
0x140015663  push    rsi
0x140015664  push    rdi
0x140015665  push    r12
0x140015667  push    r13
0x140015669  push    r14
0x14001566b  push    r15
0x14001566d  sub     rsp, 28h
0x140015671  xor     r13d, r13d
0x140015674  mov     r15, r8
0x140015677  mov     r14, rdx
0x14001567a  mov     rsi, rcx
0x14001567d  test    rcx, rcx
0x140015680  jz      short loc_140015687
0x140015682  movzx   eax, word ptr [rcx]
0x140015685  jmp     short loc_14001568A
0x140015687  mov     eax, r13d
0x14001568a  test    r14, r14
0x14001568d  jz      short loc_140015694
0x14001568f  movzx   edi, word ptr [rdx]
0x140015692  jmp     short loc_140015697
0x140015694  mov     edi, r13d
0x140015697  mov     [r8], r13
0x14001569a  test    ax, ax
0x14001569d  jnz     short loc_1400156AE
0x14001569f  test    di, di
0x1400156a2  jnz     short loc_1400156AE
0x1400156a4  mov     esi, 0C000000Dh
0x1400156a9  jmp     loc_140015744
0x1400156ae  movzx   ebp, di
0x1400156b1  mov     ecx, 102h
0x1400156b6  mov     r8d, 4855754Dh
0x1400156bc  lea     rdx, [rbp+60h]
0x1400156c0  call    cs:__imp_ExAllocatePool2
0x1400156c7  nop     dword ptr [rax+rax+00h]
0x1400156cc  mov     rbx, rax
0x1400156cf  test    rax, rax
0x1400156d2  jnz     short loc_1400156DB
0x1400156d4  mov     esi, 0C0000017h
0x1400156d9  jmp     short loc_140015744
0x1400156db  xor     edx, edx; Val
0x1400156dd  mov     rcx, rbx; void *
0x1400156e0  lea     r8d, [rdx+60h]; Size
0x1400156e4  call    memset
0x1400156e9  lea     rax, [rbx+8]
0x1400156ed  mov     dword ptr [rbx], 60710Eh
0x1400156f3  mov     dword ptr [rbx+4], 1
0x1400156fa  lea     rdx, [rbx+18h]
0x1400156fe  mov     rcx, rsi; StringIn
0x140015701  mov     [rax+8], rax
0x140015705  mov     [rax], rax
0x140015708  call    MupInitializeServerName
0x14001570d  mov     esi, eax
0x14001570f  test    eax, eax
0x140015711  js      short loc_14001573C
0x140015713  test    di, di
0x140015716  jz      short loc_140015734
0x140015718  lea     rcx, [rbx+60h]; void *
0x14001571c  mov     [rbx+42h], di
0x140015720  mov     [rbx+48h], rcx
0x140015724  mov     r8, rbp; Size
0x140015727  mov     [rbx+40h], di
0x14001572b  mov     rdx, [r14+8]; Src
0x14001572f  call    memmove
0x140015734  mov     [r15], rbx
0x140015737  mov     esi, r13d
0x14001573a  jmp     short loc_140015744
0x14001573c  mov     rcx, rbx; P
0x14001573f  call    MupiDereferenceUncHardeningConfigurationEntry
0x140015744  mov     eax, esi
0x140015746  add     rsp, 28h
0x14001574a  pop     r15
0x14001574c  pop     r14
0x14001574e  pop     r13
0x140015750  pop     r12
0x140015752  pop     rdi
0x140015753  pop     rsi
0x140015754  pop     rbp
0x140015755  pop     rbx
0x140015756  retn
```
