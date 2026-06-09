# RdsDWMDirectDriverIO::~RdsDWMDirectDriverIO(void)

- ea: `0x180007850`
- end: `0x1800078f0`
- name: `??1RdsDWMDirectDriverIO@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(RdsDWMDirectDriverIO *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007970`

## callees

- `0x180007850`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078c0`
- `GDI32!DeleteDC` at `0x180007885`
- `GDI32!DeleteDC` at `0x180007885`

## pseudocode

```c
void __fastcall RdsDWMDirectDriverIO::~RdsDWMDirectDriverIO(RdsDWMDirectDriverIO *this)
{
  HDC v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &RdsDWMDirectDriverIO::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 6) = &RdsDWMDirectDriverIO::`vftable';
  v2 = (HDC)*((_QWORD *)this + 73);
  if ( v2 )
  {
    DeleteDC(v2);
    *((_QWORD *)this + 73) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 74);
  if ( v3 != (void *)-1LL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 74) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 78);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 78) = 0;
  }
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
  *((_DWORD *)this + 7) |= 8u;
}

```

## disassembly

```asm
0x180007850  push    rbx
0x180007852  sub     rsp, 20h
0x180007856  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18000785d  mov     rbx, rcx
0x180007860  mov     [rcx], rax
0x180007863  lea     rax, ??_7RdsDWMDirectDriverIO@@6BCTSObject@@@; const RdsDWMDirectDriverIO::`vftable'{for `CTSObject'}
0x18000786a  mov     [rcx+8], rax
0x18000786e  lea     rax, ??_7RdsDWMDirectDriverIO@@6B@; const RdsDWMDirectDriverIO::`vftable'
0x180007875  mov     [rcx+30h], rax
0x180007879  mov     rcx, [rcx+248h]; hdc
0x180007880  test    rcx, rcx
0x180007883  jz      short loc_180007896
0x180007885  call    cs:__imp_DeleteDC
0x18000788b  mov     qword ptr [rbx+248h], 0
0x180007896  mov     rcx, [rbx+250h]; hObject
0x18000789d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800078a1  jz      short loc_1800078B4
0x1800078a3  call    cs:__imp_CloseHandle
0x1800078a9  mov     qword ptr [rbx+250h], 0
0x1800078b4  mov     rcx, [rbx+270h]; hObject
0x1800078bb  test    rcx, rcx
0x1800078be  jz      short loc_1800078D1
0x1800078c0  call    cs:__imp_CloseHandle
0x1800078c6  mov     qword ptr [rbx+270h], 0
0x1800078d1  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x1800078d8  mov     [rbx], rax
0x1800078db  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x1800078e2  mov     [rbx+8], rax
0x1800078e6  or      dword ptr [rbx+1Ch], 8
0x1800078ea  add     rsp, 20h
0x1800078ee  pop     rbx
0x1800078ef  retn
```
