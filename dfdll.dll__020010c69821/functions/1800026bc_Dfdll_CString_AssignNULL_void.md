# Dfdll::CString::AssignNULL(void)

- ea: `0x1800026bc`
- end: `0x18000271d`
- name: `?AssignNULL@CString@Dfdll@@IEAAJXZ`
- size: `97`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002558`
- `0x180002604`
- `0x180002b80`
- `0x180002ff8`
- `0x1800037a0`
- `0x180012140`

## callees

- `0x1800026bc`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::AssignNULL(Dfdll::CString *this)
{
  __int64 result; // rax
  char *v3; // rcx
  __int64 v4; // rax
  _DWORD *v5; // rdi
  _QWORD *v6; // rbx

  if ( !*((_DWORD *)this + 8)
    || (result = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8, 0),
        (int)result >= 0) )
  {
    *((_DWORD *)this + 8) = 0;
    v3 = (char *)this + 8;
    v4 = *((_QWORD *)this + 1);
    v5 = (_DWORD *)((char *)this + 24);
    v6 = (_QWORD *)((char *)this + 16);
    (*(void (__fastcall **)(char *, _QWORD *, _DWORD *))(v4 + 88))(v3, v6, v5);
    *v6 = 0;
    *v5 = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800026bc  mov     [rsp+arg_0], rbx
0x1800026c1  push    rdi
0x1800026c2  sub     rsp, 20h
0x1800026c6  cmp     dword ptr [rcx+20h], 0
0x1800026ca  mov     rbx, rcx
0x1800026cd  jbe     short loc_1800026E6
0x1800026cf  add     rcx, 8
0x1800026d3  xor     edx, edx
0x1800026d5  mov     rax, [rcx]
0x1800026d8  mov     rax, [rax+28h]
0x1800026dc  call    cs:__guard_dispatch_icall_fptr
0x1800026e2  test    eax, eax
0x1800026e4  js      short loc_180002712
0x1800026e6  and     dword ptr [rbx+20h], 0
0x1800026ea  lea     rcx, [rbx+8]
0x1800026ee  mov     rax, [rcx]
0x1800026f1  lea     rdi, [rcx+10h]
0x1800026f5  lea     rbx, [rcx+8]
0x1800026f9  mov     r8, rdi
0x1800026fc  mov     rdx, rbx
0x1800026ff  mov     rax, [rax+58h]
0x180002703  call    cs:__guard_dispatch_icall_fptr
0x180002709  and     qword ptr [rbx], 0
0x18000270d  and     dword ptr [rdi], 0
0x180002710  xor     eax, eax
0x180002712  mov     rbx, [rsp+28h+arg_0]
0x180002717  add     rsp, 20h
0x18000271b  pop     rdi
0x18000271c  retn
```
