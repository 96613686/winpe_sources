# Smb2BufferErrorResponse

- ea: `0x140015570`
- end: `0x14001576f`
- name: `Smb2BufferErrorResponse`
- size: `511`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, _DWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140015360`
- `0x14001c190`
- `0x140020080`
- `0x140029250`
- `0x140032700`

## callees

- `0x140015570`
- `0x14002a9ac`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400156e9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400156e9`
- `mrxsmb!SmbCseAllocateErrorBuffer` at `0x14001565d`
- `mrxsmb!SmbCseAllocateErrorBuffer` at `0x14001565d`

## pseudocode

```c
__int64 __fastcall Smb2BufferErrorResponse(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, _DWORD *a5)
{
  __int64 v5; // rdi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  const void *v10; // r14
  __int64 v11; // rax
  int ErrorBuffer; // ebx
  __int64 v13; // rcx
  PVOID v14; // rax
  __int64 result; // rax

  v5 = a4;
  if ( a3 < 0x48 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_33;
    }
    v9 = 27;
LABEL_32:
    WPP_SF_(v8->AttachedDevice, v9, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids);
LABEL_33:
    ErrorBuffer = -1073741629;
    goto LABEL_34;
  }
  v10 = (const void *)(a2 + 64);
  if ( *(_WORD *)(a2 + 64) != 9 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_33;
    }
    v9 = 28;
    goto LABEL_32;
  }
  if ( a4 > 0x11000 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_33;
    }
    v9 = 29;
    goto LABEL_32;
  }
  v11 = *(unsigned int *)(a2 + 68);
  if ( (unsigned int)v11 > a4 || v11 + 72 > (unsigned __int64)a4 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_33;
    }
    v9 = 30;
    goto LABEL_32;
  }
  ErrorBuffer = SmbCseAllocateErrorBuffer(a1, a4 - 64);
  if ( ErrorBuffer < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_33;
    }
    v9 = 31;
    goto LABEL_32;
  }
  if ( (_DWORD)v5 != a3 )
  {
    result = 3221225494LL;
    *a5 = 64;
    return result;
  }
  v13 = *(_QWORD *)(a1 + 752);
  if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
  {
    memmove(*(void **)(v13 + 24), v10, v5 - 64);
  }
  else
  {
    v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
    memmove(v14, v10, v5 - 64);
  }
LABEL_34:
  *a5 = v5;
  return (unsigned int)ErrorBuffer;
}

```

## disassembly

```asm
0x140015570  push    rbx
0x140015572  push    rbp
0x140015573  push    rsi
0x140015574  push    rdi
0x140015575  push    r14
0x140015577  push    r15
0x140015579  sub     rsp, 38h
0x14001557d  mov     edi, r9d
0x140015580  mov     esi, r8d
0x140015583  mov     rbp, rcx
0x140015586  cmp     r8d, 48h ; 'H'
0x14001558a  jnb     short loc_1400155C2
0x14001558c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015593  lea     rax, WPP_GLOBAL_Control
0x14001559a  cmp     rcx, rax
0x14001559d  jz      loc_140015750
0x1400155a3  mov     eax, [rcx+2Ch]
0x1400155a6  test    al, 1
0x1400155a8  jz      loc_140015750
0x1400155ae  cmp     byte ptr [rcx+29h], 1
0x1400155b2  jb      loc_140015750
0x1400155b8  mov     edx, 1Bh
0x1400155bd  jmp     loc_140015740
0x1400155c2  cmp     word ptr [rdx+40h], 9
0x1400155c7  lea     r14, [rdx+40h]
0x1400155cb  jz      short loc_140015603
0x1400155cd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400155d4  lea     rax, WPP_GLOBAL_Control
0x1400155db  cmp     rcx, rax
0x1400155de  jz      loc_140015750
0x1400155e4  mov     eax, [rcx+2Ch]
0x1400155e7  test    al, 1
0x1400155e9  jz      loc_140015750
0x1400155ef  cmp     byte ptr [rcx+29h], 1
0x1400155f3  jb      loc_140015750
0x1400155f9  mov     edx, 1Ch
0x1400155fe  jmp     loc_140015740
0x140015603  cmp     edi, 11000h
0x140015609  jbe     short loc_140015641
0x14001560b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015612  lea     rax, WPP_GLOBAL_Control
0x140015619  cmp     rcx, rax
0x14001561c  jz      loc_140015750
0x140015622  mov     eax, [rcx+2Ch]
0x140015625  test    al, 1
0x140015627  jz      loc_140015750
0x14001562d  cmp     byte ptr [rcx+29h], 1
0x140015631  jb      loc_140015750
0x140015637  mov     edx, 1Dh
0x14001563c  jmp     loc_140015740
0x140015641  mov     eax, [r14+4]
0x140015645  cmp     eax, edi
0x140015647  ja      loc_14001571B
0x14001564d  add     rax, 48h ; 'H'
0x140015651  cmp     rax, rdi
0x140015654  ja      loc_14001571B
0x14001565a  lea     edx, [rdi-40h]
0x14001565d  call    cs:__imp_SmbCseAllocateErrorBuffer
0x140015664  nop     dword ptr [rax+rax+00h]
0x140015669  mov     ebx, eax
0x14001566b  test    eax, eax
0x14001566d  jns     short loc_1400156A5
0x14001566f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015676  lea     rax, WPP_GLOBAL_Control
0x14001567d  cmp     rcx, rax
0x140015680  jz      loc_140015750
0x140015686  mov     eax, [rcx+2Ch]
0x140015689  test    al, 1
0x14001568b  jz      loc_140015750
0x140015691  cmp     byte ptr [rcx+29h], 1
0x140015695  jb      loc_140015750
0x14001569b  mov     edx, 1Fh
0x1400156a0  jmp     loc_140015740
0x1400156a5  cmp     edi, esi
0x1400156a7  jnz     short loc_140015706
0x1400156a9  mov     rcx, [rbp+2F0h]; MemoryDescriptorList
0x1400156b0  test    byte ptr [rcx+0Ah], 5
0x1400156b4  jz      short loc_1400156CE
0x1400156b6  mov     rax, [rcx+18h]
0x1400156ba  lea     r8, [rdi-40h]; Size
0x1400156be  mov     rcx, rax; void *
0x1400156c1  mov     rdx, r14; Src
0x1400156c4  call    memmove
0x1400156c9  jmp     loc_140015755
0x1400156ce  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400156d6  xor     r9d, r9d; RequestedAddress
0x1400156d9  xor     edx, edx; AccessMode
0x1400156db  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400156e3  mov     r8d, 1; CacheType
0x1400156e9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400156f0  nop     dword ptr [rax+rax+00h]
0x1400156f5  lea     r8, [rdi-40h]; Size
0x1400156f9  mov     rdx, r14; Src
0x1400156fc  mov     rcx, rax; void *
0x1400156ff  call    memmove
0x140015704  jmp     short loc_140015755
0x140015706  mov     rcx, [rsp+68h+arg_20]
0x14001570e  mov     eax, 0C0000016h
0x140015713  mov     dword ptr [rcx], 40h ; '@'
0x140015719  jmp     short loc_140015761
0x14001571b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015722  lea     rax, WPP_GLOBAL_Control
0x140015729  cmp     rcx, rax
0x14001572c  jz      short loc_140015750
0x14001572e  mov     eax, [rcx+2Ch]
0x140015731  test    al, 1
0x140015733  jz      short loc_140015750
0x140015735  cmp     byte ptr [rcx+29h], 1
0x140015739  jb      short loc_140015750
0x14001573b  mov     edx, 1Eh
0x140015740  mov     rcx, [rcx+18h]
0x140015744  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x14001574b  call    WPP_SF_
0x140015750  mov     ebx, 0C00000C3h
0x140015755  mov     rax, [rsp+68h+arg_20]
0x14001575d  mov     [rax], edi
0x14001575f  mov     eax, ebx
0x140015761  add     rsp, 38h
0x140015765  pop     r15
0x140015767  pop     r14
0x140015769  pop     rdi
0x14001576a  pop     rsi
0x14001576b  pop     rbp
0x14001576c  pop     rbx
0x14001576d  retn
```
