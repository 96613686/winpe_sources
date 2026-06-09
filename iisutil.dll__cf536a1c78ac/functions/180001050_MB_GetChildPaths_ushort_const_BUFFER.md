# MB::GetChildPaths(ushort const *,BUFFER *)

- ea: `0x180001050`
- end: `0x180001160`
- name: `?GetChildPaths@MB@@QEAAHPEBGPEAVBUFFER@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(MB *this, const unsigned __int16 *, struct BUFFER *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001050`
- `0x180002da0`
- `0x1800166dc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001141`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001141`

## pseudocode

```c
__int64 __fastcall MB::GetChildPaths(MB *this, const unsigned __int16 *a2, struct BUFFER *a3)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  signed int v8; // eax
  DWORD v9; // eax
  int v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  v4 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this;
  v12 = 0;
  v7 = (**v4)(v4, &IID_IMSAdminBase3_W, &v12);
  if ( v7 < 0 )
  {
    v9 = WIN32_FROM_HRESULT(v7);
    SetLastError(v9);
  }
  else
  {
    while ( 1 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD, _QWORD, int *))(*(_QWORD *)v12 + 320LL))(
             v12,
             *((unsigned int *)this + 2),
             a2,
             *((_DWORD *)a3 + 10) >> 1,
             *((_QWORD *)a3 + 4),
             &v11);
      if ( v8 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return 1;
      }
      if ( (v8 & 0x1FFF0000) != 0x70000 )
        break;
      v8 = (unsigned __int16)v8;
      if ( (unsigned __int16)v8 != 122 )
        break;
      if ( !BUFFER::Resize(a3, 2 * v11 + 2) )
        goto LABEL_11;
    }
    SetLastError(v8);
LABEL_11:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180001050  mov     rax, rsp
0x180001053  mov     [rax+10h], rbx
0x180001057  mov     [rax+18h], rsi
0x18000105b  push    rdi
0x18000105c  sub     rsp, 40h
0x180001060  mov     dword ptr [rax+8], 0
0x180001067  mov     rdi, rcx
0x18000106a  mov     rcx, [rcx]
0x18000106d  mov     rbx, r8
0x180001070  mov     qword ptr [rax+20h], 0
0x180001078  lea     r8, [rsp+48h+arg_18]
0x18000107d  mov     rsi, rdx
0x180001080  lea     rdx, IID_IMSAdminBase3_W
0x180001087  mov     rax, [rcx]
0x18000108a  mov     rax, [rax]
0x18000108d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001092  test    eax, eax
0x180001094  js      short loc_1800010FF
0x180001096  mov     rcx, [rsp+48h+arg_18]
0x18000109b  lea     rdx, [rsp+48h+arg_0]
0x1800010a0  mov     r9d, [rbx+28h]
0x1800010a4  mov     r8, rsi
0x1800010a7  mov     [rsp+48h+var_20], rdx
0x1800010ac  mov     rdx, [rbx+20h]
0x1800010b0  mov     rax, [rcx]
0x1800010b3  mov     [rsp+48h+var_28], rdx
0x1800010b8  mov     edx, [rdi+8]
0x1800010bb  shr     r9d, 1
0x1800010be  mov     rax, [rax+140h]
0x1800010c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010ca  test    eax, eax
0x1800010cc  jns     short loc_180001127
0x1800010ce  mov     ecx, eax
0x1800010d0  and     ecx, 1FFF0000h
0x1800010d6  cmp     ecx, 70000h
0x1800010dc  jnz     short loc_18000113F
0x1800010de  movzx   eax, ax
0x1800010e1  cmp     eax, 7Ah ; 'z'
0x1800010e4  jnz     short loc_18000113F
0x1800010e6  mov     edx, [rsp+48h+arg_0]
0x1800010ea  mov     rcx, rbx; this
0x1800010ed  lea     edx, ds:2[rdx*2]; unsigned int
0x1800010f4  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800010f9  test    al, al
0x1800010fb  jnz     short loc_180001096
0x1800010fd  jmp     short loc_18000114D
0x1800010ff  mov     ecx, eax; int
0x180001101  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180001106  mov     ecx, eax; dwErrCode
0x180001108  call    cs:__imp_SetLastError
0x18000110f  nop     dword ptr [rax+rax+00h]
0x180001114  xor     eax, eax
0x180001116  mov     rbx, [rsp+48h+arg_8]
0x18000111b  mov     rsi, [rsp+48h+arg_10]
0x180001120  add     rsp, 40h
0x180001124  pop     rdi
0x180001125  retn
0x180001127  mov     rcx, [rsp+48h+arg_18]
0x18000112c  mov     rax, [rcx]
0x18000112f  mov     rax, [rax+10h]
0x180001133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001138  mov     eax, 1
0x18000113d  jmp     short loc_180001116
0x18000113f  mov     ecx, eax; dwErrCode
0x180001141  call    cs:__imp_SetLastError
0x180001148  nop     dword ptr [rax+rax+00h]
0x18000114d  mov     rcx, [rsp+48h+arg_18]
0x180001152  mov     rax, [rcx]
0x180001155  mov     rax, [rax+10h]
0x180001159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000115e  jmp     short loc_180001114
```
