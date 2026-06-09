# sub_18017DFFC

- ea: `0x18017dffc`
- end: `0x18017e1af`
- name: `sub_18017DFFC`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18017e2c0`

## callees

- `0x1800dfdbc`
- `0x1800e3270`
- `0x1800ef9c0`
- `0x1800efcc0`
- `0x18017dffc`
- `0x18017e1e0`
- `0x18017ed90`
- `0x18017eeb0`
- `0x180181420`
- `0x1801838f8`
- `0x180199130`
- `0x1801f2510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017e040`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017e040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017e06b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017e06b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18017e10e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18017e10e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017e134`

## pseudocode

```c
__int64 __fastcall sub_18017DFFC(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)a1 = &off_180207178;
  *(_QWORD *)(a1 + 1288) = off_180207158;
  *(_QWORD *)(a1 + 84) = 0;
  sub_18017ED90();
  sub_180181420(a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1800));
  if ( *(_QWORD *)(a1 + 1488) )
    sub_18017E1E0();
  *(_QWORD *)(a1 + 1488) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1800));
  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 72) = 0;
  }
  v3 = *(_QWORD *)(a1 + 3216);
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 4552) )
      sub_1800DFDBC();
    sub_1800E3270(*(_QWORD *)(a1 + 3216));
    sub_1800EFCC0(*(_QWORD *)(a1 + 3216));
    v4 = *(_QWORD *)(a1 + 2032);
    if ( v4 )
    {
      sub_180199130(v4 + 8);
      *(_QWORD *)(a1 + 2032) = 0;
    }
    v5 = *(_QWORD *)(a1 + 3216);
    if ( v5 )
      sub_1800EF9C0(v5, 1);
    *(_QWORD *)(a1 + 3216) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 1800));
  CloseHandle(*(HANDLE *)(a1 + 2040));
  CloseHandle(*(HANDLE *)(a1 + 2048));
  if ( *(_QWORD *)(a1 + 1520) )
  {
    v6 = *(_QWORD *)(a1 + 1480);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
  }
  v7 = *(_QWORD *)(a1 + 1480);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *(_QWORD *)(a1 + 1480) = 0;
  }
  sub_18017EEB0(a1, 1);
  _InterlockedDecrement(&dword_180246004);
  return sub_1801838F8(a1);
}

```

## disassembly

```asm
0x18017dffc  mov     [rsp+arg_0], rbx
0x18017e001  push    rdi
0x18017e002  sub     rsp, 20h
0x18017e006  mov     rbx, rcx
0x18017e009  lea     rax, off_180207178
0x18017e010  mov     [rcx], rax
0x18017e013  lea     rax, off_180207158
0x18017e01a  mov     [rcx+508h], rax
0x18017e021  mov     qword ptr [rcx+54h], 0
0x18017e029  call    sub_18017ED90
0x18017e02e  mov     rcx, rbx
0x18017e031  call    sub_180181420
0x18017e036  lea     rdi, [rbx+708h]
0x18017e03d  mov     rcx, rdi; lpCriticalSection
0x18017e040  call    cs:EnterCriticalSection
0x18017e047  nop     dword ptr [rax+rax+00h]
0x18017e04c  mov     rcx, [rbx+5D0h]
0x18017e053  test    rcx, rcx
0x18017e056  jz      short loc_18017E05D
0x18017e058  call    sub_18017E1E0
0x18017e05d  mov     qword ptr [rbx+5D0h], 0
0x18017e068  mov     rcx, rdi; lpCriticalSection
0x18017e06b  call    cs:LeaveCriticalSection
0x18017e072  nop     dword ptr [rax+rax+00h]
0x18017e077  mov     rcx, [rbx+48h]
0x18017e07b  test    rcx, rcx
0x18017e07e  jz      short loc_18017E095
0x18017e080  mov     rax, [rcx]
0x18017e083  mov     rax, [rax+10h]
0x18017e087  call    cs:__guard_dispatch_icall_fptr
0x18017e08d  mov     qword ptr [rbx+48h], 0
0x18017e095  mov     rax, [rbx+0C90h]
0x18017e09c  test    rax, rax
0x18017e09f  jz      short loc_18017E10B
0x18017e0a1  mov     rcx, [rax+11C8h]
0x18017e0a8  test    rcx, rcx
0x18017e0ab  jz      short loc_18017E0B2
0x18017e0ad  call    sub_1800DFDBC
0x18017e0b2  mov     rcx, [rbx+0C90h]
0x18017e0b9  call    sub_1800E3270
0x18017e0be  mov     rcx, [rbx+0C90h]
0x18017e0c5  call    sub_1800EFCC0
0x18017e0ca  mov     rcx, [rbx+7F0h]
0x18017e0d1  test    rcx, rcx
0x18017e0d4  jz      short loc_18017E0EA
0x18017e0d6  add     rcx, 8
0x18017e0da  call    sub_180199130
0x18017e0df  mov     qword ptr [rbx+7F0h], 0
0x18017e0ea  mov     rcx, [rbx+0C90h]
0x18017e0f1  test    rcx, rcx
0x18017e0f4  jz      short loc_18017E100
0x18017e0f6  mov     edx, 1
0x18017e0fb  call    sub_1800EF9C0
0x18017e100  mov     qword ptr [rbx+0C90h], 0
0x18017e10b  mov     rcx, rdi; lpCriticalSection
0x18017e10e  call    cs:__imp_DeleteCriticalSection
0x18017e115  nop     dword ptr [rax+rax+00h]
0x18017e11a  mov     rcx, [rbx+7F8h]; hObject
0x18017e121  call    cs:CloseHandle
0x18017e128  nop     dword ptr [rax+rax+00h]
0x18017e12d  mov     rcx, [rbx+800h]; hObject
0x18017e134  call    cs:CloseHandle
0x18017e13b  nop     dword ptr [rax+rax+00h]
0x18017e140  mov     rdx, [rbx+5F0h]
0x18017e147  test    rdx, rdx
0x18017e14a  jz      short loc_18017E165
0x18017e14c  mov     rcx, [rbx+5C8h]
0x18017e153  test    rcx, rcx
0x18017e156  jz      short loc_18017E165
0x18017e158  mov     rax, [rcx]
0x18017e15b  mov     rax, [rax+28h]
0x18017e15f  call    cs:__guard_dispatch_icall_fptr
0x18017e165  mov     rcx, [rbx+5C8h]
0x18017e16c  test    rcx, rcx
0x18017e16f  jz      short loc_18017E189
0x18017e171  mov     rax, [rcx]
0x18017e174  mov     rax, [rax+10h]
0x18017e178  call    cs:__guard_dispatch_icall_fptr
0x18017e17e  mov     qword ptr [rbx+5C8h], 0
0x18017e189  mov     edx, 1
0x18017e18e  mov     rcx, rbx
0x18017e191  call    sub_18017EEB0
0x18017e196  lock dec cs:dword_180246004
0x18017e19d  mov     rcx, rbx
0x18017e1a0  mov     rbx, [rsp+28h+arg_0]
0x18017e1a5  add     rsp, 20h
0x18017e1a9  pop     rdi
0x18017e1aa  jmp     sub_1801838F8
```
