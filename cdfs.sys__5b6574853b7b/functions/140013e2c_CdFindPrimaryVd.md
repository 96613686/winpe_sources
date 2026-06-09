# CdFindPrimaryVd

- ea: `0x140013e2c`
- end: `0x1400140c6`
- name: `CdFindPrimaryVd`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400142d8`
- `0x140015090`

## callees

- `0x140001114`
- `0x140003300`
- `0x14000fcb0`
- `0x140010c38`
- `0x140013e2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013f94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013f94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb02`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140013e9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140013e9f`

## pseudocode

```c
char __fastcall CdFindPrimaryVd(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, char a5, char a6)
{
  unsigned int v6; // r15d
  __int64 Buffer; // r14
  unsigned int v10; // esi
  char v11; // r13
  int v12; // r12d
  _BYTE *PoolWithTag; // rax
  int v14; // ecx
  _BYTE *v15; // rbx
  int v16; // eax
  _BYTE *v17; // rcx
  unsigned int *v18; // rdx
  bool v19; // zf
  int v20; // ebx
  int v21; // r15d
  char v22; // r9
  int v23; // eax
  _BYTE *v24; // rax
  int DeviceObject; // [rsp+28h] [rbp-70h]
  __int64 v26; // [rsp+A0h] [rbp+8h]
  unsigned int v27; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+20h]

  v28 = a4;
  v26 = a1;
  v6 = a4;
  Buffer = a3;
  if ( (*(_DWORD *)(a2 + 48) & 0x80u) != 0 )
    return 0;
  v10 = 1;
  v11 = 0;
  while ( !v11 && v10 <= 2 )
  {
    v12 = 0;
    v27 = 0;
    if ( v10 == 1 )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x554u, 0x63746443u);
      v15 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, 0x554u);
      v16 = CdPerformDevIoCtrl(v14, 147512, *(_QWORD *)(a2 + 16), (_DWORD)v15, 1364, DeviceObject, 1, 0);
      if ( v16 == -1073741670 )
        CdRaiseStatusEx(v26, -1073741670, 0, 983040, 2896);
      if ( v16 < 0 || v15[2] == v15[3] )
      {
        v10 = 2;
      }
      else
      {
        LODWORD(a3) = 4;
        v17 = v15 + 11;
        v18 = &v27;
        do
        {
          *(_BYTE *)v18 = *v17;
          v18 = (unsigned int *)((char *)v18 + 1);
          --v17;
          v19 = (_DWORD)a3 == 1;
          a3 = (unsigned int)(a3 - 1);
        }
        while ( !v19 );
        v12 = v27 / v6;
        v27 /= v6;
      }
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      a1 = v26;
    }
    v20 = 16;
    v21 = 0;
    while ( 1 )
    {
      v22 = v10 == 1 || a5;
      if ( !CdReadSectors(
              a1,
              (union _LARGE_INTEGER)((unsigned __int64)(unsigned int)(v20 + v12) << 11),
              a3,
              v22,
              (PVOID)Buffer,
              *(PDEVICE_OBJECT *)(a2 + 16)) )
        break;
      if ( CdIsoId == *(_DWORD *)(Buffer + 1) && byte_140007154 == *(_BYTE *)(Buffer + 5) )
      {
        v23 = 2;
      }
      else
      {
        if ( CdHsgId != *(_DWORD *)(Buffer + 9) || byte_14000715C != *(_BYTE *)(Buffer + 13) )
          break;
        v23 = 1;
      }
      v21 |= v23;
      if ( *(_BYTE *)(Buffer + 8LL * (v21 & 1) + 6) != 1 )
        break;
      v24 = (_BYTE *)(Buffer + 8);
      if ( (v21 & 1) == 0 )
        v24 = (_BYTE *)Buffer;
      if ( *v24 == 0xFF )
        break;
      if ( *v24 == 1 )
      {
        if ( !a6 )
        {
          *(_DWORD *)(a2 + 48) |= v21;
          *(_DWORD *)(a2 + 96) = v12;
          *(_DWORD *)(a2 + 100) = v20;
          *(_DWORD *)(a2 + 104) = v20;
        }
        v11 = 1;
        break;
      }
      ++v20;
      a1 = v26;
    }
    ++v10;
    a1 = v26;
    v6 = v28;
  }
  return v11;
}

```

## disassembly

```asm
0x140013e2c  mov     [rsp+arg_18], r9d
0x140013e31  mov     qword ptr [rsp+arg_0], rcx
0x140013e36  push    rbx
0x140013e37  push    rsi
0x140013e38  push    rdi
0x140013e39  push    r12
0x140013e3b  push    r13
0x140013e3d  push    r14
0x140013e3f  push    r15
0x140013e41  sub     rsp, 60h
0x140013e45  mov     r15d, r9d
0x140013e48  mov     r14, r8
0x140013e4b  mov     rdi, rdx
0x140013e4e  mov     eax, [rdx+30h]
0x140013e51  test    al, al
0x140013e53  jns     short loc_140013E5C
0x140013e55  xor     al, al
0x140013e57  jmp     loc_140014093
0x140013e5c  mov     esi, 1
0x140013e61  xor     r13b, r13b
0x140013e64  test    r13b, r13b
0x140013e67  jnz     loc_140014090
0x140013e6d  cmp     esi, 2
0x140013e70  ja      loc_140014090
0x140013e76  xor     r12d, r12d
0x140013e79  mov     [rsp+98h+arg_8], r12d
0x140013e81  cmp     esi, 1
0x140013e84  jnz     loc_140013FA8
0x140013e8a  mov     [rsp+98h+var_50], r12
0x140013e8f  mov     edx, 554h; NumberOfBytes
0x140013e94  mov     ecx, 411h; PoolType
0x140013e99  mov     r8d, 63746443h; Tag
0x140013e9f  call    cs:__imp_ExAllocatePoolWithTag
0x140013ea6  nop     dword ptr [rax+rax+00h]
0x140013eab  mov     rbx, rax
0x140013eae  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x140013eb5  jnz     short loc_140013ECC
0x140013eb7  test    rax, rax
0x140013eba  jz      short loc_140013ECC
0x140013ebc  xor     edx, edx; Val
0x140013ebe  mov     r8d, 554h; Size
0x140013ec4  mov     rcx, rax; void *
0x140013ec7  call    memset
0x140013ecc  mov     [rsp+98h+var_50], rbx
0x140013ed1  mov     [rsp+98h+var_60], 0
0x140013eda  mov     [rsp+98h+var_68], 1
0x140013edf  mov     dword ptr [rsp+98h+Buffer], 554h
0x140013ee7  mov     r9, rbx
0x140013eea  mov     r8, [rdi+10h]
0x140013eee  mov     edx, 24038h
0x140013ef3  call    CdPerformDevIoCtrl
0x140013ef8  cmp     eax, 0C000009Ah
0x140013efd  jz      loc_1400140A4
0x140013f03  test    eax, eax
0x140013f05  js      short loc_140013F81
0x140013f07  mov     al, [rbx+3]
0x140013f0a  cmp     [rbx+2], al
0x140013f0d  jz      short loc_140013F81
0x140013f0f  mov     [rsp+98h+var_40], 0
0x140013f18  mov     [rsp+98h+var_48], 0
0x140013f21  mov     [rsp+98h+var_58], 0
0x140013f29  mov     r8d, 4
0x140013f2f  mov     [rsp+98h+var_58], r8d
0x140013f34  lea     rcx, [rbx+0Bh]
0x140013f38  mov     [rsp+98h+var_40], rcx
0x140013f3d  lea     rdx, [rsp+98h+arg_8]
0x140013f45  mov     [rsp+98h+var_48], rdx
0x140013f4a  mov     al, [rcx]
0x140013f4c  mov     [rdx], al
0x140013f4e  inc     rdx
0x140013f51  mov     [rsp+98h+var_48], rdx
0x140013f56  dec     rcx
0x140013f59  mov     [rsp+98h+var_40], rcx
0x140013f5e  add     r8d, 0FFFFFFFFh
0x140013f62  mov     [rsp+98h+var_58], r8d
0x140013f67  jnz     short loc_140013F4A
0x140013f69  xor     edx, edx
0x140013f6b  mov     eax, [rsp+98h+arg_8]
0x140013f72  div     r15d
0x140013f75  mov     r12d, eax
0x140013f78  mov     [rsp+98h+arg_8], eax
0x140013f7f  jmp     short loc_140013F8A
0x140013f81  mov     esi, 2
0x140013f86  mov     [rsp+98h+var_54], esi
0x140013f8a  test    rbx, rbx
0x140013f8d  jz      short loc_140013FA0
0x140013f8f  xor     edx, edx; Tag
0x140013f91  mov     rcx, rbx; P
0x140013f94  call    cs:__imp_ExFreePoolWithTag
0x140013f9b  nop     dword ptr [rax+rax+00h]
0x140013fa0  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x140013fa8  mov     ebx, 10h
0x140013fad  xor     r15d, r15d
0x140013fb0  cmp     esi, 1
0x140013fb3  jz      short loc_140013FC4
0x140013fb5  cmp     [rsp+98h+arg_20], 0
0x140013fbd  jnz     short loc_140013FC4
0x140013fbf  xor     r9d, r9d
0x140013fc2  jmp     short loc_140013FC7
0x140013fc4  mov     r9b, 1; int
0x140013fc7  lea     edx, [rbx+r12]
0x140013fcb  shl     rdx, 0Bh; int
0x140013fcf  mov     rax, [rdi+10h]
0x140013fd3  mov     [rsp+98h+DeviceObject], rax; DeviceObject
0x140013fd8  mov     [rsp+98h+Buffer], r14; Buffer
0x140013fdd  call    CdReadSectors
0x140013fe2  test    al, al
0x140013fe4  jz      loc_140014079
0x140013fea  mov     eax, cs:CdIsoId
0x140013ff0  cmp     eax, [r14+1]
0x140013ff4  jnz     short loc_140014009
0x140013ff6  mov     al, cs:byte_140007154
0x140013ffc  cmp     al, [r14+5]
0x140014000  jnz     short loc_140014009
0x140014002  mov     eax, 2
0x140014007  jmp     short loc_140014026
0x140014009  mov     eax, cs:CdHsgId
0x14001400f  cmp     eax, [r14+9]
0x140014013  jnz     short loc_140014079
0x140014015  mov     al, cs:byte_14000715C
0x14001401b  cmp     al, [r14+0Dh]
0x14001401f  jnz     short loc_140014079
0x140014021  mov     eax, 1
0x140014026  or      eax, r15d
0x140014029  mov     r15d, eax
0x14001402c  and     eax, 1
0x14001402f  mov     ecx, eax
0x140014031  cmp     byte ptr [r14+rax*8+6], 1
0x140014037  jnz     short loc_140014079
0x140014039  lea     rax, [r14+8]
0x14001403d  test    ecx, ecx
0x14001403f  cmovz   rax, r14
0x140014043  mov     cl, [rax]
0x140014045  cmp     cl, 0FFh
0x140014048  jz      short loc_140014079
0x14001404a  cmp     cl, 1
0x14001404d  jz      short loc_14001405E
0x14001404f  inc     ebx
0x140014051  mov     rcx, qword ptr [rsp+98h+arg_0]
0x140014059  jmp     loc_140013FB0
0x14001405e  cmp     [rsp+98h+arg_28], 0
0x140014066  jnz     short loc_140014076
0x140014068  or      [rdi+30h], r15d
0x14001406c  mov     [rdi+60h], r12d
0x140014070  mov     [rdi+64h], ebx
0x140014073  mov     [rdi+68h], ebx
0x140014076  mov     r13b, 1
0x140014079  inc     esi
0x14001407b  mov     rcx, qword ptr [rsp+98h+arg_0]
0x140014083  mov     r15d, [rsp+98h+arg_18]
0x14001408b  jmp     loc_140013E64
0x140014090  mov     al, r13b
0x140014093  add     rsp, 60h
0x140014097  pop     r15
0x140014099  pop     r14
0x14001409b  pop     r13
0x14001409d  pop     r12
0x14001409f  pop     rdi
0x1400140a0  pop     rsi
0x1400140a1  pop     rbx
0x1400140a2  retn
0x1400140a4  mov     dword ptr [rsp+98h+Buffer], 0B50h
0x1400140ac  mov     r9d, 0F0000h
0x1400140b2  xor     r8d, r8d
0x1400140b5  mov     edx, eax
0x1400140b7  mov     rcx, qword ptr [rsp+98h+arg_0]
0x1400140bf  call    CdRaiseStatusEx
0x14001baee  push    rbp
0x14001baf0  sub     rsp, 40h
0x14001baf4  mov     rbp, rdx
0x14001baf7  mov     rcx, [rbp+48h]; P
0x14001bafb  test    rcx, rcx
0x14001bafe  jz      short loc_14001BB16
0x14001bb00  xor     edx, edx; Tag
0x14001bb02  call    cs:__imp_ExFreePoolWithTag
0x14001bb09  nop     dword ptr [rax+rax+00h]
0x14001bb0e  mov     qword ptr [rbp+48h], 0
0x14001bb16  add     rsp, 40h
0x14001bb1a  pop     rbp
0x14001bb1b  retn
```
