# DiskGetInfoExceptionInformation

- ea: `0x14000e31c`
- end: `0x14000e500`
- name: `DiskGetInfoExceptionInformation`
- size: `484`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010490`
- `0x140014200`

## callees

- `0x140004078`
- `0x1400043dc`
- `0x14000e31c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4e6`
- `ntoskrnl!ExAllocatePool2` at `0x14000e33d`
- `ntoskrnl!ExAllocatePool2` at `0x14000e33d`
- `CLASSPNP!ClassFindModePage` at `0x14000e422`
- `CLASSPNP!ClassFindModePage` at `0x14000e422`
- `CLASSPNP!ClassModeSense` at `0x14000e39b`
- `CLASSPNP!ClassModeSense` at `0x14000e3bb`
- `CLASSPNP!ClassModeSense` at `0x14000e39b`
- `CLASSPNP!ClassModeSense` at `0x14000e3bb`

## pseudocode

```c
__int64 __fastcall DiskGetInfoExceptionInformation(__int64 a1, __int64 a2)
{
  CHAR *Pool2; // rax
  CHAR *v5; // rsi
  ULONG v7; // ecx
  int v8; // edi
  ULONG v9; // edi
  _DWORD *ModePage; // rax
  const char *v11; // r9

  Pool2 = (CHAR *)ExAllocatePool2(72, 192, 1095000915);
  v5 = Pool2;
  if ( Pool2 )
  {
    v7 = ClassModeSense(*(PDEVICE_OBJECT *)(a1 + 8), Pool2, 0xC0u, 0x1Cu);
    if ( v7 >= 4 || (v7 = ClassModeSense(*(PDEVICE_OBJECT *)(a1 + 8), v5, 0xC0u, 0x1Cu), v7 >= 4) )
    {
      v9 = (unsigned __int8)*v5 + 1;
      if ( v7 <= v9 )
        v9 = v7;
      ModePage = ClassFindModePage(v5, v9, 0x1Cu, 1u);
      if ( ModePage )
      {
        if ( ModePage + 3 <= (_DWORD *)&v5[v9] )
        {
          v8 = 0;
          *(_QWORD *)a2 = *(_QWORD *)ModePage;
          *(_DWORD *)(a2 + 8) = ModePage[2];
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
          }
          v8 = -1073741823;
        }
      }
      else
      {
        v8 = -1073741637;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v11 = "does";
        if ( v8 < 0 )
          v11 = "does not";
        WPP_SF_sq(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          (unsigned int)WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
          (_DWORD)v11,
          *(_QWORD *)(a1 + 8));
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      v8 = -1073741435;
    }
    ExFreePoolWithTag(v5, 0);
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000e31c  push    rbx
0x14000e31e  push    rbp
0x14000e31f  push    rsi
0x14000e320  push    rdi
0x14000e321  push    r14
0x14000e323  sub     rsp, 30h
0x14000e327  mov     ebx, 0C0h
0x14000e32c  mov     r14, rdx
0x14000e32f  mov     rbp, rcx
0x14000e332  mov     r8d, 41446353h
0x14000e338  mov     edx, ebx
0x14000e33a  lea     ecx, [rbx-78h]
0x14000e33d  call    cs:__imp_ExAllocatePool2
0x14000e344  nop     dword ptr [rax+rax+00h]
0x14000e349  mov     rsi, rax
0x14000e34c  test    rax, rax
0x14000e34f  jnz     short loc_14000E38E
0x14000e351  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e358  lea     rbx, WPP_GLOBAL_Control
0x14000e35f  cmp     rcx, rbx
0x14000e362  jz      short loc_14000E384
0x14000e364  mov     eax, [rcx+2Ch]
0x14000e367  test    al, 40h
0x14000e369  jz      short loc_14000E384
0x14000e36b  cmp     byte ptr [rcx+29h], 2
0x14000e36f  jb      short loc_14000E384
0x14000e371  mov     rcx, [rcx+18h]
0x14000e375  lea     edx, [rsi+2Dh]
0x14000e378  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e37f  call    WPP_SF_
0x14000e384  mov     eax, 0C000009Ah
0x14000e389  jmp     loc_14000E4F4
0x14000e38e  mov     rcx, [rbp+8]; DeviceObject
0x14000e392  mov     r9b, 1Ch; PageMode
0x14000e395  mov     r8d, ebx; Length
0x14000e398  mov     rdx, rsi; ModeSenseBuffer
0x14000e39b  call    cs:__imp_ClassModeSense
0x14000e3a2  nop     dword ptr [rax+rax+00h]
0x14000e3a7  mov     ecx, eax
0x14000e3a9  cmp     eax, 4
0x14000e3ac  jnb     short loc_14000E40D
0x14000e3ae  mov     rcx, [rbp+8]; DeviceObject
0x14000e3b2  mov     r9b, 1Ch; PageMode
0x14000e3b5  mov     r8d, ebx; Length
0x14000e3b8  mov     rdx, rsi; ModeSenseBuffer
0x14000e3bb  call    cs:__imp_ClassModeSense
0x14000e3c2  nop     dword ptr [rax+rax+00h]
0x14000e3c7  mov     ecx, eax
0x14000e3c9  cmp     eax, 4
0x14000e3cc  jnb     short loc_14000E40D
0x14000e3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3d5  lea     rbx, WPP_GLOBAL_Control
0x14000e3dc  cmp     rcx, rbx
0x14000e3df  jz      short loc_14000E403
0x14000e3e1  mov     eax, [rcx+2Ch]
0x14000e3e4  test    al, 40h
0x14000e3e6  jz      short loc_14000E403
0x14000e3e8  cmp     byte ptr [rcx+29h], 2
0x14000e3ec  jb      short loc_14000E403
0x14000e3ee  mov     rcx, [rcx+18h]
0x14000e3f2  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e3f9  mov     edx, 2Eh ; '.'
0x14000e3fe  call    WPP_SF_
0x14000e403  mov     edi, 0C0000185h
0x14000e408  jmp     loc_14000E4E1
0x14000e40d  movzx   edi, byte ptr [rsi]
0x14000e410  mov     r9b, 1; Use6Byte
0x14000e413  inc     edi
0x14000e415  mov     r8b, 1Ch; PageMode
0x14000e418  cmp     ecx, edi
0x14000e41a  cmovbe  edi, ecx
0x14000e41d  mov     rcx, rsi; ModeSenseBuffer
0x14000e420  mov     edx, edi; Length
0x14000e422  call    cs:__imp_ClassFindModePage
0x14000e429  nop     dword ptr [rax+rax+00h]
0x14000e42e  lea     rbx, WPP_GLOBAL_Control
0x14000e435  test    rax, rax
0x14000e438  jz      short loc_14000E491
0x14000e43a  mov     edx, edi
0x14000e43c  lea     rcx, [rax+0Ch]
0x14000e440  add     rdx, rsi
0x14000e443  cmp     rcx, rdx
0x14000e446  jbe     short loc_14000E47D
0x14000e448  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e44f  cmp     rcx, rbx
0x14000e452  jz      short loc_14000E476
0x14000e454  mov     eax, [rcx+2Ch]
0x14000e457  test    al, 40h
0x14000e459  jz      short loc_14000E476
0x14000e45b  cmp     byte ptr [rcx+29h], 2
0x14000e45f  jb      short loc_14000E476
0x14000e461  mov     rcx, [rcx+18h]
0x14000e465  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e46c  mov     edx, 2Fh ; '/'
0x14000e471  call    WPP_SF_
0x14000e476  mov     edi, 0C0000001h
0x14000e47b  jmp     short loc_14000E496
0x14000e47d  movsd   xmm0, qword ptr [rax]
0x14000e481  xor     edi, edi
0x14000e483  movsd   qword ptr [r14], xmm0
0x14000e488  mov     eax, [rax+8]
0x14000e48b  mov     [r14+8], eax
0x14000e48f  jmp     short loc_14000E496
0x14000e491  mov     edi, 0C00000BBh
0x14000e496  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e49d  cmp     rcx, rbx
0x14000e4a0  jz      short loc_14000E4E1
0x14000e4a2  mov     eax, [rcx+2Ch]
0x14000e4a5  test    al, 40h
0x14000e4a7  jz      short loc_14000E4E1
0x14000e4a9  cmp     byte ptr [rcx+29h], 4
0x14000e4ad  jb      short loc_14000E4E1
0x14000e4af  mov     r8, [rbp+8]
0x14000e4b3  lea     rax, aDoesNot; "does not"
0x14000e4ba  mov     rcx, [rcx+18h]
0x14000e4be  lea     r9, aDoes; "does"
0x14000e4c5  test    edi, edi
0x14000e4c7  mov     [rsp+58h+var_38], r8
0x14000e4cc  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e4d3  mov     edx, 30h ; '0'
0x14000e4d8  cmovs   r9, rax
0x14000e4dc  call    WPP_SF_sq
0x14000e4e1  xor     edx, edx; Tag
0x14000e4e3  mov     rcx, rsi; P
0x14000e4e6  call    cs:__imp_ExFreePoolWithTag
0x14000e4ed  nop     dword ptr [rax+rax+00h]
0x14000e4f2  mov     eax, edi
0x14000e4f4  add     rsp, 30h
0x14000e4f8  pop     r14
0x14000e4fa  pop     rdi
0x14000e4fb  pop     rsi
0x14000e4fc  pop     rbp
0x14000e4fd  pop     rbx
0x14000e4fe  retn
```
