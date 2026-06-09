# Imapi2Utility::ConvertDescriptorArrayToULONGArray(IWriteSpeedDescriptor * *,ulong,ulong * *)

- ea: `0x1800431a8`
- end: `0x1800432b8`
- name: `?ConvertDescriptorArrayToULONGArray@Imapi2Utility@@YAJPEAPEAUIWriteSpeedDescriptor@@KPEAPEAK@Z`
- size: `272`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IWriteSpeedDescriptor **, unsigned int, unsigned int **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18004499c`
- `0x180047cd8`

## callees

- `0x1800140f4`
- `0x180016778`
- `0x1800431a8`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800431d2`
- `KERNEL32!LocalAlloc` at `0x1800431d2`
- `KERNEL32!LocalFree` at `0x180043294`
- `KERNEL32!LocalFree` at `0x180043294`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::ConvertDescriptorArrayToULONGArray(
        Imapi2Utility *this,
        struct IWriteSpeedDescriptor **a2,
        _QWORD *a3,
        unsigned int **a4)
{
  unsigned int v4; // r14d
  _DWORD *v7; // rsi
  PVOID *v8; // rcx
  int v9; // edi
  __int64 v10; // rbp
  __int64 v11; // rcx
  int v13; // [rsp+58h] [rbp+10h] BYREF

  v4 = (unsigned int)a2;
  v7 = LocalAlloc(0x40u, 4LL * (unsigned int)a2);
  if ( v7 )
  {
    v10 = 0;
    v9 = 0;
    while ( (unsigned int)v10 < v4 )
    {
      v11 = *((_QWORD *)this + v10);
      v13 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 72LL))(v11, &v13);
      v7[v10] = v13;
      v10 = (unsigned int)(v10 + 1);
      if ( v9 < 0 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_11;
      }
    }
    *a3 = v7;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v9 = -2147024882;
LABEL_11:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      WPP_SF_d(v8[2], 117, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, (unsigned int)v9);
    if ( v7 )
      LocalFree(v7);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800431a8  mov     [rsp+arg_0], rbx
0x1800431ad  mov     [rsp+arg_10], rbp
0x1800431b2  push    rsi
0x1800431b3  push    rdi
0x1800431b4  push    r12
0x1800431b6  push    r14
0x1800431b8  push    r15
0x1800431ba  sub     rsp, 20h
0x1800431be  mov     r14d, edx
0x1800431c1  mov     r12, rcx
0x1800431c4  mov     edx, edx
0x1800431c6  mov     ecx, 40h ; '@'; uFlags
0x1800431cb  shl     rdx, 2; uBytes
0x1800431cf  mov     r15, r8
0x1800431d2  call    cs:__imp_LocalAlloc
0x1800431d8  mov     rsi, rax
0x1800431db  lea     rax, WPP_GLOBAL_Control
0x1800431e2  test    rsi, rsi
0x1800431e5  jnz     short loc_180043220
0x1800431e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431ee  cmp     rcx, rax
0x1800431f1  jz      short loc_180043219
0x1800431f3  test    byte ptr [rcx+1Ch], 4
0x1800431f7  jz      short loc_180043219
0x1800431f9  cmp     byte ptr [rcx+19h], 4
0x1800431fd  jb      short loc_180043219
0x1800431ff  mov     rcx, [rcx+10h]
0x180043203  lea     edx, [rsi+74h]
0x180043206  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004320d  call    WPP_SF_
0x180043212  mov     rcx, cs:WPP_GLOBAL_Control
0x180043219  mov     edi, 8007000Eh
0x18004321e  jmp     short loc_18004325C
0x180043220  xor     ebp, ebp
0x180043222  xor     edi, edi
0x180043224  cmp     ebp, r14d
0x180043227  jnb     short loc_18004329C
0x180043229  mov     rcx, [r12+rbp*8]
0x18004322d  lea     rdx, [rsp+48h+arg_8]
0x180043232  mov     [rsp+48h+arg_8], 0
0x18004323a  mov     rax, [rcx]
0x18004323d  mov     rax, [rax+48h]
0x180043241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043246  mov     edi, eax
0x180043248  mov     eax, [rsp+48h+arg_8]
0x18004324c  mov     [rsi+rbp*4], eax
0x18004324f  inc     ebp
0x180043251  test    edi, edi
0x180043253  jns     short loc_180043224
0x180043255  mov     rcx, cs:WPP_GLOBAL_Control
0x18004325c  lea     rax, WPP_GLOBAL_Control
0x180043263  cmp     rcx, rax
0x180043266  jz      short loc_18004328C
0x180043268  test    byte ptr [rcx+1Ch], 4
0x18004326c  jz      short loc_18004328C
0x18004326e  cmp     byte ptr [rcx+19h], 4
0x180043272  jb      short loc_18004328C
0x180043274  mov     rcx, [rcx+10h]
0x180043278  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004327f  mov     edx, 75h ; 'u'
0x180043284  mov     r9d, edi
0x180043287  call    WPP_SF_d
0x18004328c  test    rsi, rsi
0x18004328f  jz      short loc_18004329F
0x180043291  mov     rcx, rsi; hMem
0x180043294  call    cs:__imp_LocalFree
0x18004329a  jmp     short loc_18004329F
0x18004329c  mov     [r15], rsi
0x18004329f  mov     rbx, [rsp+48h+arg_0]
0x1800432a4  mov     eax, edi
0x1800432a6  mov     rbp, [rsp+48h+arg_10]
0x1800432ab  add     rsp, 20h
0x1800432af  pop     r15
0x1800432b1  pop     r14
0x1800432b3  pop     r12
0x1800432b5  pop     rdi
0x1800432b6  pop     rsi
0x1800432b7  retn
```
