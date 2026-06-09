# GenerateUIResponseEvent

- ea: `0x180023b6c`
- end: `0x180023d7a`
- name: `GenerateUIResponseEvent`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180024c40`
- `0x18002bd50`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000cf70`
- `0x18000d500`
- `0x180010d40`
- `0x180013440`
- `0x1800214f0`
- `0x180023b6c`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x180023c4e`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180023c9e`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180023c4e`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180023c9e`

## pseudocode

```c
__int64 __fastcall GenerateUIResponseEvent(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7)
{
  unsigned int v7; // edi
  __int64 v10; // r12
  unsigned int v12; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v19; // [rsp+60h] [rbp+30h] BYREF

  v7 = *(_DWORD *)(a1 + 20);
  v10 = a2;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v12 = OneXCreateEvent(&v19, a7 != 0 ? 8 : 32, 3, a1);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_26;
    v15 = 60;
LABEL_25:
    WPP_SF_dd(v14[7], v15, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v7, v12);
LABEL_26:
    OneXDeleteEvent(v19);
    goto LABEL_27;
  }
  *(_DWORD *)(v19 + 40) = 2;
  *(_QWORD *)(v19 + 48) = v10;
  *(_DWORD *)(v19 + 56) = 5;
  *(_DWORD *)(v19 + 60) = a3;
  v12 = AllocateAndCopyPointerData(v19 + 64, a4, a3);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_26;
    v15 = 61;
    goto LABEL_25;
  }
  v16 = a5;
  v17 = a6;
  *(_DWORD *)(v19 + 72) = 5;
  *(_DWORD *)(v19 + 76) = v16;
  v12 = AllocateAndCopyPointerData(v19 + 80, v17, v16);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_26;
    v15 = 62;
    goto LABEL_25;
  }
  if ( a7 )
  {
    v12 = QueueGlobalEvent(v19);
    v13 = v12;
    if ( v12 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      v15 = 63;
      goto LABEL_25;
    }
  }
  else
  {
    v12 = QueueSupplicantEvent(v19);
    v13 = v12;
    if ( v12 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      v15 = 64;
      goto LABEL_25;
    }
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180023b6c  mov     [rsp-28h+arg_8], rbx
0x180023b71  mov     [rsp-28h+arg_10], rdi
0x180023b76  push    rbp
0x180023b77  push    r12
0x180023b79  push    r13
0x180023b7b  push    r14
0x180023b7d  push    r15
0x180023b7f  mov     rbp, rsp
0x180023b82  sub     rsp, 30h
0x180023b86  mov     edi, [rcx+14h]
0x180023b89  mov     r15, r9
0x180023b8c  mov     r14d, r8d
0x180023b8f  mov     r12d, edx
0x180023b92  mov     rbx, rcx
0x180023b95  mov     [rbp+arg_0], 0
0x180023b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ba4  lea     r13, WPP_GLOBAL_Control
0x180023bab  cmp     rcx, r13
0x180023bae  jz      short loc_180023BCE
0x180023bb0  test    dword ptr [rcx+44h], 800h
0x180023bb7  jz      short loc_180023BCE
0x180023bb9  mov     rcx, [rcx+38h]
0x180023bbd  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180023bc4  mov     edx, 3Bh ; ';'
0x180023bc9  call    WPP_SF_
0x180023bce  mov     eax, [rbp+arg_30]
0x180023bd1  lea     rcx, [rbp+arg_0]
0x180023bd5  neg     eax
0x180023bd7  mov     r9, rbx
0x180023bda  mov     r8d, 3
0x180023be0  sbb     edx, edx
0x180023be2  and     edx, 0FFFFFFE8h
0x180023be5  add     edx, 20h ; ' '
0x180023be8  call    OneXCreateEvent
0x180023bed  mov     ebx, eax
0x180023bef  test    eax, eax
0x180023bf1  jz      short loc_180023C17
0x180023bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bfa  cmp     rcx, r13
0x180023bfd  jz      loc_180023D2A
0x180023c03  test    byte ptr [rcx+44h], 1
0x180023c07  jz      loc_180023D2A
0x180023c0d  mov     edx, 3Ch ; '<'
0x180023c12  jmp     loc_180023D13
0x180023c17  mov     rax, [rbp+arg_0]
0x180023c1b  mov     r8d, r14d
0x180023c1e  mov     rdx, r15
0x180023c21  mov     dword ptr [rax+28h], 2
0x180023c28  mov     rax, [rbp+arg_0]
0x180023c2c  mov     [rax+30h], r12
0x180023c30  mov     r12d, 5
0x180023c36  mov     rax, [rbp+arg_0]
0x180023c3a  mov     [rax+38h], r12d
0x180023c3e  mov     rax, [rbp+arg_0]
0x180023c42  mov     [rax+3Ch], r14d
0x180023c46  mov     rcx, [rbp+arg_0]
0x180023c4a  add     rcx, 40h ; '@'
0x180023c4e  call    cs:__imp_AllocateAndCopyPointerData
0x180023c54  mov     ebx, eax
0x180023c56  test    eax, eax
0x180023c58  jz      short loc_180023C7E
0x180023c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c61  cmp     rcx, r13
0x180023c64  jz      loc_180023D2A
0x180023c6a  test    byte ptr [rcx+44h], 1
0x180023c6e  jz      loc_180023D2A
0x180023c74  lea     edx, [r12+38h]
0x180023c79  jmp     loc_180023D13
0x180023c7e  mov     rax, [rbp+arg_0]
0x180023c82  mov     r8d, [rbp+arg_20]
0x180023c86  mov     rdx, [rbp+arg_28]
0x180023c8a  mov     [rax+48h], r12d
0x180023c8e  mov     rax, [rbp+arg_0]
0x180023c92  mov     [rax+4Ch], r8d
0x180023c96  mov     rcx, [rbp+arg_0]
0x180023c9a  add     rcx, 50h ; 'P'
0x180023c9e  call    cs:__imp_AllocateAndCopyPointerData
0x180023ca4  mov     ebx, eax
0x180023ca6  test    eax, eax
0x180023ca8  jz      short loc_180023CC3
0x180023caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cb1  cmp     rcx, r13
0x180023cb4  jz      short loc_180023D2A
0x180023cb6  test    byte ptr [rcx+44h], 1
0x180023cba  jz      short loc_180023D2A
0x180023cbc  mov     edx, 3Eh ; '>'
0x180023cc1  jmp     short loc_180023D13
0x180023cc3  cmp     [rbp+arg_30], 0
0x180023cc7  mov     rcx, [rbp+arg_0]
0x180023ccb  jz      short loc_180023CF1
0x180023ccd  call    QueueGlobalEvent
0x180023cd2  mov     ebx, eax
0x180023cd4  test    eax, eax
0x180023cd6  jz      short loc_180023D33
0x180023cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cdf  cmp     rcx, r13
0x180023ce2  jz      short loc_180023D2A
0x180023ce4  test    byte ptr [rcx+44h], 1
0x180023ce8  jz      short loc_180023D2A
0x180023cea  mov     edx, 3Fh ; '?'
0x180023cef  jmp     short loc_180023D13
0x180023cf1  call    QueueSupplicantEvent
0x180023cf6  mov     ebx, eax
0x180023cf8  test    eax, eax
0x180023cfa  jz      short loc_180023D33
0x180023cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d03  cmp     rcx, r13
0x180023d06  jz      short loc_180023D2A
0x180023d08  test    byte ptr [rcx+44h], 1
0x180023d0c  jz      short loc_180023D2A
0x180023d0e  mov     edx, 40h ; '@'
0x180023d13  mov     rcx, [rcx+38h]
0x180023d17  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180023d1e  mov     r9d, edi
0x180023d21  mov     [rsp+30h+var_10], eax
0x180023d25  call    WPP_SF_dd
0x180023d2a  mov     rcx, [rbp+arg_0]
0x180023d2e  call    OneXDeleteEvent
0x180023d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d3a  cmp     rcx, r13
0x180023d3d  jz      short loc_180023D60
0x180023d3f  test    dword ptr [rcx+44h], 800h
0x180023d46  jz      short loc_180023D60
0x180023d48  mov     rcx, [rcx+38h]
0x180023d4c  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180023d53  mov     edx, 41h ; 'A'
0x180023d58  mov     r9d, ebx
0x180023d5b  call    WPP_SF_D
0x180023d60  mov     rdi, [rsp+30h+arg_10]
0x180023d65  mov     eax, ebx
0x180023d67  mov     rbx, [rsp+30h+arg_8]
0x180023d6c  add     rsp, 30h
0x180023d70  pop     r15
0x180023d72  pop     r14
0x180023d74  pop     r13
0x180023d76  pop     r12
0x180023d78  pop     rbp
0x180023d79  retn
```
