# ActuallySetVolume(_MCIGRAPHIC *)

- ea: `0x180001dfc`
- end: `0x180001e73`
- name: `?ActuallySetVolume@@YAJPEAU_MCIGRAPHIC@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023d4`
- `0x180005634`

## callees

- `0x180001dfc`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ActuallySetVolume(struct _MCIGRAPHIC *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax

  v1 = -10000;
  v2 = 4294957296LL;
  if ( !*((_DWORD *)a1 + 55) )
    v2 = *((unsigned int *)a1 + 57);
  if ( *((_DWORD *)a1 + 58) || (v4 = *((_DWORD *)a1 + 60), v1 = v4, v4 <= (int)v2) )
  {
    v5 = v1 - v2;
  }
  else
  {
    v5 = v4 - v2;
    v2 = (unsigned int)v4;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 23) + 56LL))(*((_QWORD *)a1 + 23), v2);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 23) + 72LL))(*((_QWORD *)a1 + 23), v5);
  return result;
}

```

## disassembly

```asm
0x180001dfc  mov     [rsp+arg_0], rbx
0x180001e01  push    rdi
0x180001e02  sub     rsp, 20h
0x180001e06  cmp     dword ptr [rcx+0DCh], 0
0x180001e0d  mov     ebx, 0FFFFD8F0h
0x180001e12  mov     edx, ebx
0x180001e14  mov     rdi, rcx
0x180001e17  jnz     short loc_180001E1F
0x180001e19  mov     edx, [rcx+0E4h]
0x180001e1f  cmp     dword ptr [rcx+0E8h], 0
0x180001e26  jnz     short loc_180001E3A
0x180001e28  mov     eax, [rcx+0F0h]
0x180001e2e  mov     ebx, eax
0x180001e30  cmp     eax, edx
0x180001e32  jle     short loc_180001E3A
0x180001e34  sub     ebx, edx
0x180001e36  mov     edx, eax
0x180001e38  jmp     short loc_180001E3C
0x180001e3a  sub     ebx, edx
0x180001e3c  mov     rcx, [rcx+0B8h]
0x180001e43  mov     rax, [rcx]
0x180001e46  mov     rax, [rax+38h]
0x180001e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e4f  test    eax, eax
0x180001e51  js      short loc_180001E68
0x180001e53  mov     rcx, [rdi+0B8h]
0x180001e5a  mov     edx, ebx
0x180001e5c  mov     rax, [rcx]
0x180001e5f  mov     rax, [rax+48h]
0x180001e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e68  mov     rbx, [rsp+28h+arg_0]
0x180001e6d  add     rsp, 20h
0x180001e71  pop     rdi
0x180001e72  retn
```
