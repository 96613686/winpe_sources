# CShareEventContext::StartEvents(_MI_Context *)

- ea: `0x18000dcc0`
- end: `0x18000ddcc`
- name: `?StartEvents@CShareEventContext@@QEAAEPEAU_MI_Context@@@Z`
- size: `268`
- prototype: `unsigned __int8 __fastcall(CShareEventContext *__hidden this, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009190`

## callees

- `0x180001220`
- `0x180009094`
- `0x18000dcc0`
- `0x1800169bc`
- `0x180037010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000dcff`
- `KERNEL32!CloseHandle` at `0x18000dd8a`
- `KERNEL32!CloseHandle` at `0x18000dcff`
- `KERNEL32!CloseHandle` at `0x18000dd8a`
- `KERNEL32!CreateThread` at `0x18000dd65`
- `KERNEL32!CreateThread` at `0x18000dd65`

## pseudocode

```c
char __fastcall CShareEventContext::StartEvents(CShareEventContext *this, struct _MI_Context *a2)
{
  char v5; // di
  void *v6; // rcx
  _BYTE *v7; // rax
  unsigned int v8; // edx
  HANDLE Thread; // rax
  void *v10; // rcx
  CNfsEtwEvents *v11; // rcx

  if ( *((_BYTE *)this + 80) )
    return 0;
  v5 = 0;
  (**(void (__fastcall ***)(CShareEventContext *))this)(this);
  if ( !*((_BYTE *)this + 80) )
  {
    v6 = (void *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = a2;
    v7 = operator new(0x20u);
    if ( v7 )
    {
      *(_QWORD *)v7 = 0;
      v7[8] = 0;
      *((_QWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 3) = -1;
    }
    else
    {
      v7 = 0;
    }
    *((_QWORD *)this + 9) = v7;
    if ( v7 )
    {
      if ( !CNfsEtwEvents::StartSession((CNfsEtwEvents *)v7) )
      {
        Thread = CreateThread(0, 0, ShareEvents, this, 0, 0);
        *((_QWORD *)this + 7) = Thread;
        if ( Thread )
          *((_BYTE *)this + 80) = 1;
      }
    }
    v5 = *((_BYTE *)this + 80);
    if ( !v5 )
    {
      v10 = (void *)*((_QWORD *)this + 7);
      if ( v10 )
      {
        CloseHandle(v10);
        *((_QWORD *)this + 7) = 0;
      }
      v11 = (CNfsEtwEvents *)*((_QWORD *)this + 9);
      if ( v11 )
      {
        CNfsEtwEvents::`scalar deleting destructor'(v11, v8);
        *((_QWORD *)this + 9) = 0;
      }
      *((_QWORD *)this + 8) = 0;
      v5 = 0;
      *((_BYTE *)this + 80) = 0;
    }
  }
  (*(void (__fastcall **)(CShareEventContext *))(*(_QWORD *)this + 8LL))(this);
  return v5;
}

```

## disassembly

```asm
0x18000dcc0  push    rbx
0x18000dcc2  push    rbp
0x18000dcc3  push    rsi
0x18000dcc4  push    rdi
0x18000dcc5  sub     rsp, 38h
0x18000dcc9  xor     ebp, ebp
0x18000dccb  mov     rsi, rdx
0x18000dcce  mov     rbx, rcx
0x18000dcd1  cmp     [rcx+50h], bpl
0x18000dcd5  jz      short loc_18000DCDE
0x18000dcd7  xor     al, al
0x18000dcd9  jmp     loc_18000DDC3
0x18000dcde  mov     rax, [rcx]
0x18000dce1  mov     dil, bpl
0x18000dce4  mov     rax, [rax]
0x18000dce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcec  cmp     [rbx+50h], bpl
0x18000dcf0  jnz     loc_18000DDB1
0x18000dcf6  mov     rcx, [rbx+38h]; hObject
0x18000dcfa  test    rcx, rcx
0x18000dcfd  jz      short loc_18000DD09
0x18000dcff  call    cs:__imp_CloseHandle
0x18000dd05  mov     [rbx+38h], rbp
0x18000dd09  mov     ecx, 20h ; ' '; Size
0x18000dd0e  mov     [rbx+40h], rsi
0x18000dd12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dd17  mov     [rsp+58h+arg_0], rax
0x18000dd1c  test    rax, rax
0x18000dd1f  jz      short loc_18000DD36
0x18000dd21  mov     [rax], rbp
0x18000dd24  mov     [rax+8], bpl
0x18000dd28  mov     [rax+10h], rbp
0x18000dd2c  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000dd34  jmp     short loc_18000DD39
0x18000dd36  mov     rax, rbp
0x18000dd39  mov     [rbx+48h], rax
0x18000dd3d  test    rax, rax
0x18000dd40  jz      short loc_18000DD78
0x18000dd42  mov     rcx, rax; this
0x18000dd45  call    ?StartSession@CNfsEtwEvents@@QEAAKXZ; CNfsEtwEvents::StartSession(void)
0x18000dd4a  test    eax, eax
0x18000dd4c  jnz     short loc_18000DD78
0x18000dd4e  mov     [rsp+58h+lpThreadId], rbp; lpThreadId
0x18000dd53  lea     r8, ?ShareEvents@@YAKPEAX@Z; lpStartAddress
0x18000dd5a  mov     r9, rbx; lpParameter
0x18000dd5d  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x18000dd61  xor     edx, edx; dwStackSize
0x18000dd63  xor     ecx, ecx; lpThreadAttributes
0x18000dd65  call    cs:__imp_CreateThread
0x18000dd6b  mov     [rbx+38h], rax
0x18000dd6f  test    rax, rax
0x18000dd72  jz      short loc_18000DD78
0x18000dd74  mov     byte ptr [rbx+50h], 1
0x18000dd78  mov     dil, [rbx+50h]
0x18000dd7c  test    dil, dil
0x18000dd7f  jnz     short loc_18000DDB1
0x18000dd81  mov     rcx, [rbx+38h]; hObject
0x18000dd85  test    rcx, rcx
0x18000dd88  jz      short loc_18000DD94
0x18000dd8a  call    cs:__imp_CloseHandle
0x18000dd90  mov     [rbx+38h], rbp
0x18000dd94  mov     rcx, [rbx+48h]; this
0x18000dd98  test    rcx, rcx
0x18000dd9b  jz      short loc_18000DDA6
0x18000dd9d  call    ??_GCNfsEtwEvents@@QEAAPEAXI@Z; CNfsEtwEvents::`scalar deleting destructor'(uint)
0x18000dda2  mov     [rbx+48h], rbp
0x18000dda6  mov     [rbx+40h], rbp
0x18000ddaa  mov     dil, bpl
0x18000ddad  mov     [rbx+50h], bpl
0x18000ddb1  mov     rcx, [rbx]
0x18000ddb4  mov     rax, [rcx+8]
0x18000ddb8  mov     rcx, rbx
0x18000ddbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddc0  mov     al, dil
0x18000ddc3  add     rsp, 38h
0x18000ddc7  pop     rdi
0x18000ddc8  pop     rsi
0x18000ddc9  pop     rbp
0x18000ddca  pop     rbx
0x18000ddcb  retn
```
