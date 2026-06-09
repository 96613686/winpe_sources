# CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)

- ea: `0x18002701c`
- end: `0x1800270c3`
- name: `?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z`
- size: `167`
- prototype: `bool __high(const unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, unsigned int, enum _NAMESPACETYPE)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024434`
- `0x180024eb0`
- `0x180025e20`
- `0x1800263a4`
- `0x180027c4c`
- `0x180028550`

## callees

- `0x18002701c`
- `0x180029d90`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002709c`
- `msvcrt!_wcsnicmp` at `0x18002709c`

## pseudocode

```c
bool __fastcall CXMLReader::IsMatch(
        __int64 a1,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        wchar_t *String2,
        int a6,
        int a7)
{
  unsigned int v7; // r14d
  char v9; // bl
  int v10; // esi
  const wchar_t *v11; // rbp

  v7 = a3 - (a4 != 0 ? a4 + 1 : 0);
  if ( v7 != a6 )
    return 0;
  v9 = 0;
  if ( a4 )
  {
    v10 = a7;
    a6 = 0;
    v11 = &a2[a4 + 1];
    if ( a7 != 6
      && ((unsigned int)CCollectionList::LookUpByKey((CCollectionList *)(a1 + 160), a2, a4, (enum _NAMESPACETYPE *)&a6)
       || a6 != v10) )
    {
      return v9;
    }
  }
  else
  {
    v11 = a2;
  }
  return _wcsnicmp(v11, String2, v7) == 0;
}

```

## disassembly

```asm
0x18002701c  push    rbx
0x18002701e  push    rbp
0x18002701f  push    rsi
0x180027020  push    rdi
0x180027021  push    r14
0x180027023  sub     rsp, 20h
0x180027027  mov     edi, r9d
0x18002702a  mov     eax, r9d
0x18002702d  neg     eax
0x18002702f  mov     r14d, r8d
0x180027032  sbb     r11d, r11d
0x180027035  lea     r10d, [rdi+1]
0x180027039  and     r11d, r10d
0x18002703c  sub     r14d, r11d
0x18002703f  cmp     r14d, [rsp+48h+arg_28]
0x180027044  jz      short loc_18002704A
0x180027046  xor     al, al
0x180027048  jmp     short loc_1800270B7
0x18002704a  xor     bl, bl
0x18002704c  test    r9d, r9d
0x18002704f  jz      short loc_18002708E
0x180027051  mov     esi, [rsp+48h+arg_30]
0x180027058  lea     rbp, [rdx+2]
0x18002705c  mov     [rsp+48h+arg_28], 0
0x180027064  lea     rbp, [rbp+rdi*2+0]
0x180027069  cmp     esi, 6
0x18002706c  jz      short loc_180027091
0x18002706e  add     rcx, 0A0h; this
0x180027075  lea     r9, [rsp+48h+arg_28]; enum _NAMESPACETYPE *
0x18002707a  mov     r8d, edi; unsigned int
0x18002707d  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEAW4_NAMESPACETYPE@@@Z; CCollectionList::LookUpByKey(ushort *,ulong,_NAMESPACETYPE *)
0x180027082  test    eax, eax
0x180027084  jnz     short loc_1800270B5
0x180027086  cmp     [rsp+48h+arg_28], esi
0x18002708a  jz      short loc_180027091
0x18002708c  jmp     short loc_1800270B5
0x18002708e  mov     rbp, rdx
0x180027091  mov     rdx, [rsp+48h+String2]; String2
0x180027096  mov     rcx, rbp; String1
0x180027099  mov     r8d, r14d; MaxCount
0x18002709c  call    cs:__imp__wcsnicmp
0x1800270a3  nop     dword ptr [rax+rax+00h]
0x1800270a8  movzx   ebx, bl
0x1800270ab  mov     ecx, 1
0x1800270b0  test    eax, eax
0x1800270b2  cmovz   ebx, ecx
0x1800270b5  mov     al, bl
0x1800270b7  add     rsp, 20h
0x1800270bb  pop     r14
0x1800270bd  pop     rdi
0x1800270be  pop     rsi
0x1800270bf  pop     rbp
0x1800270c0  pop     rbx
0x1800270c1  retn
```
