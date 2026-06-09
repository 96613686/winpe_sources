# CSecurityHeader::GetNextSectionSafe(char * const)

- ea: `0x14000239c`
- end: `0x14000245a`
- name: `?GetNextSectionSafe@CSecurityHeader@@QEBAPEADQEAD@Z`
- size: `190`
- prototype: `char *__fastcall(CSecurityHeader *__hidden this, char *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002d24`

## callees

- `0x140002304`
- `0x14000239c`
- `0x140002ee8`

## pseudocode

```c
char *__fastcall CSecurityHeader::GetNextSectionSafe(CSecurityHeader *this, char *const a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rax
  unsigned __int64 v15[7]; // [rsp+20h] [rbp-38h] BYREF
  bool v16; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((unsigned __int16 *)this + 1);
  v5 = (v2 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v5 < v2 )
    return 0;
  v6 = *((unsigned __int16 *)this + 2);
  v7 = (v6 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v7 < v6 )
    return 0;
  v8 = *((unsigned __int16 *)this + 3);
  v9 = (v8 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v9 < v8 )
    return 0;
  v10 = *((unsigned int *)this + 2);
  v11 = (v10 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v11 < v10 )
    return 0;
  v12 = *((unsigned int *)this + 3);
  v16 = 0;
  if ( ((v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL) < v12 )
    return 0;
  v15[0] = v5;
  v15[1] = v7;
  v15[2] = v9;
  v15[3] = v11;
  v15[4] = (v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  v13 = SafeAddPointersEx(5, v15, &v16);
  if ( v16 )
    return 0;
  else
    return GetNextSectionPtrSafe((unsigned __int64)this, 0x10u, v13, a2);
}

```

## disassembly

```asm
0x14000239c  mov     r11, rsp
0x14000239f  mov     [r11+10h], rbx
0x1400023a3  push    rdi
0x1400023a4  sub     rsp, 50h
0x1400023a8  movzx   eax, word ptr [rcx+2]
0x1400023ac  mov     rdi, rdx
0x1400023af  mov     rbx, rcx
0x1400023b2  lea     r8, [rax+3]
0x1400023b6  and     r8, 0FFFFFFFFFFFFFFFCh
0x1400023ba  cmp     r8, rax
0x1400023bd  jb      loc_14000244C
0x1400023c3  movzx   eax, word ptr [rcx+4]
0x1400023c7  lea     rcx, [rax+3]
0x1400023cb  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400023cf  cmp     rcx, rax
0x1400023d2  jb      short loc_14000244C
0x1400023d4  movzx   eax, word ptr [rbx+6]
0x1400023d8  lea     rdx, [rax+3]
0x1400023dc  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1400023e0  cmp     rdx, rax
0x1400023e3  jb      short loc_14000244C
0x1400023e5  mov     eax, [rbx+8]
0x1400023e8  lea     r9, [rax+3]
0x1400023ec  and     r9, 0FFFFFFFFFFFFFFFCh
0x1400023f0  cmp     r9, rax
0x1400023f3  jb      short loc_14000244C
0x1400023f5  mov     eax, [rbx+0Ch]
0x1400023f8  mov     [rsp+58h+arg_0], 0
0x1400023fd  lea     r10, [rax+3]
0x140002401  and     r10, 0FFFFFFFFFFFFFFFCh
0x140002405  cmp     r10, rax
0x140002408  jb      short loc_14000244C
0x14000240a  mov     [r11-38h], r8
0x14000240e  lea     r8, [r11+8]; bool *
0x140002412  mov     [r11-30h], rcx
0x140002416  mov     ecx, 5; int
0x14000241b  mov     [r11-28h], rdx
0x14000241f  lea     rdx, [r11-38h]; unsigned __int64 *
0x140002423  mov     [r11-20h], r9
0x140002427  mov     [r11-18h], r10
0x14000242b  call    ?SafeAddPointersEx@@YA_KHQEA_KPEA_N@Z; SafeAddPointersEx(int,unsigned __int64 * const,bool *)
0x140002430  cmp     [rsp+58h+arg_0], 0
0x140002435  jnz     short loc_14000244C
0x140002437  mov     r9, rdi; char *
0x14000243a  mov     r8, rax; unsigned __int64
0x14000243d  mov     edx, 10h; unsigned __int64
0x140002442  mov     rcx, rbx; unsigned __int64
0x140002445  call    ?GetNextSectionPtrSafe@@YAPEAD_K00PEAD@Z; GetNextSectionPtrSafe(unsigned __int64,unsigned __int64,unsigned __int64,char *)
0x14000244a  jmp     short loc_14000244E
0x14000244c  xor     eax, eax
0x14000244e  mov     rbx, [rsp+58h+arg_8]
0x140002453  add     rsp, 50h
0x140002457  pop     rdi
0x140002458  retn
```
