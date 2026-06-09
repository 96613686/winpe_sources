# CWMWriterInputPin::GetAllocatorRequirements(_AllocatorProperties *)

- ea: `0x1800140a0`
- end: `0x1800141a3`
- name: `?GetAllocatorRequirements@CWMWriterInputPin@@UEAAJPEAU_AllocatorProperties@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, struct _AllocatorProperties *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001460`
- `0x1800140a0`
- `0x18001e5b9`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::GetAllocatorRequirements(
        CWMWriterInputPin *this,
        struct _AllocatorProperties *a2)
{
  bool v2; // zf
  int v4; // esi
  int v5; // ebx
  __int64 result; // rax
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+28h] [rbp-20h] BYREF

  v2 = *((_QWORD *)this - 21) == 0;
  v7 = 0;
  if ( v2 )
  {
    return (unsigned int)-2147220983;
  }
  else
  {
    v4 = 64;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 16) + 312LL) + 56LL))(
           *(_QWORD *)(*((_QWORD *)this + 16) + 312LL),
           *((unsigned int *)this + 45),
           &v7);
    if ( v5 >= 0 )
    {
      if ( !v7 )
      {
LABEL_10:
        a2->cBuffers = v4;
        result = 0;
        a2->cbBuffer = 0x2000;
        *(_QWORD *)&a2->cbAlign = 1;
        return result;
      }
      Buf2 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 24LL))(v7, &Buf2);
      if ( v5 >= 0 && !memcmp_0(&WMMEDIATYPE_Video, &Buf2, 0x10u) )
        v4 = 3;
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v5 >= 0 )
      goto LABEL_10;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800140a0  mov     r11, rsp
0x1800140a3  mov     [r11+18h], rbx
0x1800140a7  mov     [r11+20h], rsi
0x1800140ab  push    rdi
0x1800140ac  sub     rsp, 40h
0x1800140b0  mov     rax, cs:__security_cookie
0x1800140b7  xor     rax, rsp
0x1800140ba  mov     [rsp+48h+var_10], rax
0x1800140bf  cmp     qword ptr [rcx-0A8h], 0
0x1800140c7  mov     rdi, rdx
0x1800140ca  mov     rdx, rcx
0x1800140cd  mov     qword ptr [r11-28h], 0
0x1800140d5  jz      loc_18001417F
0x1800140db  mov     rax, [rcx+80h]
0x1800140e2  lea     r8, [r11-28h]
0x1800140e6  mov     edx, [rdx+0B4h]
0x1800140ec  mov     esi, 40h ; '@'
0x1800140f1  mov     rcx, [rax+138h]
0x1800140f8  mov     rax, [rcx]
0x1800140fb  mov     rax, [rax+38h]
0x1800140ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014104  mov     ebx, eax
0x180014106  test    eax, eax
0x180014108  js      short loc_180014150
0x18001410a  mov     rcx, [rsp+48h+var_28]
0x18001410f  test    rcx, rcx
0x180014112  jz      short loc_18001416A
0x180014114  xorps   xmm0, xmm0
0x180014117  lea     rdx, [rsp+48h+Buf2]
0x18001411c  movups  [rsp+48h+Buf2], xmm0
0x180014121  mov     rax, [rcx]
0x180014124  mov     rax, [rax+18h]
0x180014128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001412d  mov     ebx, eax
0x18001412f  test    eax, eax
0x180014131  js      short loc_180014150
0x180014133  lea     r8d, [rsi-30h]; Size
0x180014137  lea     rdx, [rsp+48h+Buf2]; Buf2
0x18001413c  lea     rcx, WMMEDIATYPE_Video; Buf1
0x180014143  call    memcmp_0
0x180014148  test    eax, eax
0x18001414a  lea     ecx, [rsi-3Dh]
0x18001414d  cmovz   esi, ecx
0x180014150  mov     rcx, [rsp+48h+var_28]
0x180014155  test    rcx, rcx
0x180014158  jz      short loc_180014166
0x18001415a  mov     rax, [rcx]
0x18001415d  mov     rax, [rax+10h]
0x180014161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014166  test    ebx, ebx
0x180014168  js      short loc_180014184
0x18001416a  mov     [rdi], esi
0x18001416c  xor     eax, eax
0x18001416e  mov     dword ptr [rdi+4], 2000h
0x180014175  mov     qword ptr [rdi+8], 1
0x18001417d  jmp     short loc_180014186
0x18001417f  mov     ebx, 80040209h
0x180014184  mov     eax, ebx
0x180014186  mov     rcx, [rsp+48h+var_10]
0x18001418b  xor     rcx, rsp; StackCookie
0x18001418e  call    __security_check_cookie
0x180014193  mov     rbx, [rsp+48h+arg_10]
0x180014198  mov     rsi, [rsp+48h+arg_18]
0x18001419d  add     rsp, 40h
0x1800141a1  pop     rdi
0x1800141a2  retn
```
