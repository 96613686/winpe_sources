# NcaConfigMgrGetString

- ea: `0x18000673c`
- end: `0x1800067d3`
- name: `NcaConfigMgrGetString`
- size: `151`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007b58`
- `0x18000ae34`
- `0x180018c40`

## callees

- `0x180004f34`
- `0x18000673c`
- `0x180019784`
- `0x180019c70`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrGetString(int a1, __int64 a2)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  void *v6; // rcx
  int v7; // eax

  if ( a2 )
  {
    v3 = 0;
    if ( a1 == 2 )
    {
      v6 = (void *)xmmword_180028BF8;
    }
    else
    {
      v6 = 0;
      if ( a1 == 7 )
        v6 = (void *)*((_QWORD *)&xmmword_180028C08 + 1);
    }
    v7 = NcaStringCopy(v6);
    if ( v7 < 0 )
    {
      v3 = NcaHResultToWindowsError((unsigned int)v7);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 65;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 64;
LABEL_13:
      WPP_SF_d(v4[2], v5, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000673c  push    rbx
0x18000673e  sub     rsp, 20h
0x180006742  mov     eax, ecx
0x180006744  test    rdx, rdx
0x180006747  jnz     short loc_18000676A
0x180006749  lea     ebx, [rdx+57h]
0x18000674c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006753  lea     rax, WPP_GLOBAL_Control
0x18000675a  cmp     rcx, rax
0x18000675d  jz      short loc_1800067CA
0x18000675f  test    byte ptr [rcx+1Ch], 1
0x180006763  jz      short loc_1800067CA
0x180006765  lea     edx, [rbx-17h]
0x180006768  jmp     short loc_1800067B7
0x18000676a  xor     ebx, ebx
0x18000676c  cmp     eax, 2
0x18000676f  jnz     short loc_18000677A
0x180006771  mov     rcx, qword ptr cs:xmmword_180028BF8
0x180006778  jmp     short loc_180006787
0x18000677a  xor     ecx, ecx
0x18000677c  cmp     eax, 7
0x18000677f  cmovz   rcx, qword ptr cs:xmmword_180028C08+8; Src
0x180006787  call    NcaStringCopy
0x18000678c  test    eax, eax
0x18000678e  jns     short loc_1800067CA
0x180006790  mov     ecx, eax
0x180006792  call    NcaHResultToWindowsError
0x180006797  mov     ebx, eax
0x180006799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067a0  lea     rax, WPP_GLOBAL_Control
0x1800067a7  cmp     rcx, rax
0x1800067aa  jz      short loc_1800067CA
0x1800067ac  test    byte ptr [rcx+1Ch], 1
0x1800067b0  jz      short loc_1800067CA
0x1800067b2  mov     edx, 41h ; 'A'
0x1800067b7  mov     rcx, [rcx+10h]
0x1800067bb  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800067c2  mov     r9d, ebx
0x1800067c5  call    WPP_SF_d
0x1800067ca  mov     eax, ebx
0x1800067cc  add     rsp, 20h
0x1800067d0  pop     rbx
0x1800067d1  retn
```
