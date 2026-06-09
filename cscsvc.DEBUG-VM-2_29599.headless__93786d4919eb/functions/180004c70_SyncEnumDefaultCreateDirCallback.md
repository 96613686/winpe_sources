# SyncEnumDefaultCreateDirCallback

- ea: `0x180004c70`
- end: `0x180005028`
- name: `SyncEnumDefaultCreateDirCallback`
- size: `952`
- prototype: `__int64 __fastcall(int, int, int, int, int, NTSTATUS Status, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180004220`
- `0x180005900`

## callees

- `0x180004c70`
- `0x1800223c0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18004fef4`
- `0x18004ff34`
- `0x180074984`
- `0x18007514c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180004f65`
- `ntdll!RtlNtStatusToDosError` at `0x180004f65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d23`

## string_xrefs

- `0x180004eb3`: `SyncEnumNewContext: ParentDirContext: 0x%p FullPath: 0x%p`
- `0x180004f08`: `SyncEnumDefaultCreateDirCallback: Ctx: 0x%p NewRemote: 0x%p NewLocal: 0x%p NewContext: 0x%p`
- `0x180004dbf`: `SyncEnumDefaultCreateDirCallback: SyncStatus: 0x%x OpenStatus: 0x%x FullPath: 0x%p EnterDir: 0x%p`
- `0x180004f8c`: `SyncEnumDefaultCreateDirCallback: Failed to allocate new Context`
- `0x180004ff8`: `SyncEnumDefaultCreateDirCallback: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncEnumDefaultCreateDirCallback(
        __int64 a1,
        HANDLE *a2,
        HANDLE *a3,
        _QWORD *a4,
        unsigned int a5,
        unsigned int Status,
        _WORD *a7,
        _BYTE *a8)
{
  unsigned int v11; // ebp
  CObjectMonitor *v12; // rax
  _WORD *v13; // rdi
  __int64 v14; // rax
  unsigned int v16; // esi
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  _WORD *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r8
  _WORD *v27; // rcx
  __int64 v28; // rbx

  v11 = 0;
  v12 = WPP_GLOBAL_Control;
  v13 = a7;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncEnumDefaultCreateDirCallback: Ctx: 0x%p NewRemote: 0x%p NewLocal: 0x%p NewContext: 0x%p",
        a1,
        a2,
        a3,
        a4);
      WPP_SF_qqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        40,
        WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids,
        a1,
        a2,
        a3,
        a4);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncEnumDefaultCreateDirCallback: SyncStatus: 0x%x OpenStatus: 0x%x FullPath: 0x%p EnterDir: 0x%p",
        a5,
        Status,
        a7,
        a8);
      WPP_SF_DDqq(*((_QWORD *)WPP_GLOBAL_Control + 12), v22, v23, a5, Status, a7, a8);
    }
  }
  **(_DWORD **)(a1 + 16) |= a5;
  if ( (**(_DWORD **)(a1 + 16) & 0x600) != 0 )
  {
    v28 = *(_QWORD *)(a1 + 16);
    *(_DWORD *)(v28 + 4) = RtlNtStatusToDosError(Status);
  }
  if ( *a8 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewContext: ParentDirContext: 0x%p FullPath: 0x%p", a1, a7);
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, a1, a7);
    }
    v14 = -1;
    while ( a7[++v14] != 0 )
      ;
    ++NumAlloc;
    v16 = v14 + 1;
    v17 = (unsigned int)(2 * (v14 + 1) + 32);
    TotalAlloc += v17;
    ProcessHeap = GetProcessHeap();
    v19 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v17);
    v20 = v19;
    if ( v19 )
    {
      v24 = v19 + 4;
      *v19 = *(_QWORD *)a1;
      v19[1] = *(_QWORD *)(a1 + 16);
      v19[2] = 0;
      v19[3] = v19 + 4;
      v25 = 2147483646;
      v26 = v16;
      if ( v16 - 1 > 0x7FFFFFFE )
      {
        if ( v16 )
          *v24 = 0;
      }
      else
      {
        do
        {
          if ( !v25 )
            break;
          if ( !*v13 )
            break;
          *v24++ = *v13++;
          --v25;
          --v26;
        }
        while ( v26 );
        v27 = v24 - 1;
        if ( v26 )
          v27 = v24;
        *v27 = 0;
      }
    }
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewContext: 0x%p", v20);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, v20);
    }
    *a4 = v20;
    if ( v20 )
    {
      *a8 = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumDefaultCreateDirCallback: Failed to allocate new Context");
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids);
      }
      **(_DWORD **)(a1 + 16) |= 0x600u;
      if ( *a2 )
      {
        SyncCloseFile(*a2);
        *a2 = 0;
      }
      if ( *a3 )
      {
        SyncCloseFile(*a3);
        *a3 = 0;
      }
      v11 = -1073741670;
      *a8 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumDefaultCreateDirCallback: 0x%x", v11);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 43, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180004c70  mov     [rsp+arg_8], rdx
0x180004c75  push    rbx
0x180004c76  push    rbp
0x180004c77  push    rsi
0x180004c78  push    rdi
0x180004c79  push    r12
0x180004c7b  push    r13
0x180004c7d  push    r14
0x180004c7f  push    r15
0x180004c81  sub     rsp, 48h
0x180004c85  mov     r12, r9
0x180004c88  mov     r13, r8
0x180004c8b  mov     r15, rcx
0x180004c8e  xor     ebp, ebp
0x180004c90  mov     rax, cs:WPP_GLOBAL_Control
0x180004c97  lea     rcx, WPP_GLOBAL_Control
0x180004c9e  mov     r14, [rsp+88h+arg_38]
0x180004ca6  mov     rdi, [rsp+88h+arg_30]
0x180004cae  mov     esi, [rsp+88h+Status]
0x180004cb5  mov     ebx, [rsp+88h+arg_20]
0x180004cbc  cmp     rax, rcx
0x180004cbf  jnz     loc_180004D97
0x180004cc5  mov     rax, [r15+10h]
0x180004cc9  or      [rax], ebx
0x180004ccb  mov     rax, [r15+10h]
0x180004ccf  test    dword ptr [rax], 600h
0x180004cd5  jnz     loc_180004F60
0x180004cdb  cmp     [r14], bpl
0x180004cde  jz      loc_180004E9A
0x180004ce4  mov     rax, cs:WPP_GLOBAL_Control
0x180004ceb  cmp     rax, rcx
0x180004cee  jnz     loc_180004EA6
0x180004cf4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004cfb  nop     dword ptr [rax+rax+00h]
0x180004d00  cmp     [rdi+rax*2+2], bp
0x180004d05  lea     rax, [rax+1]
0x180004d09  jnz     short loc_180004D00
0x180004d0b  inc     cs:NumAlloc
0x180004d12  lea     esi, [rax+1]
0x180004d15  lea     ebx, ds:20h[rsi*2]
0x180004d1c  add     cs:TotalAlloc, rbx
0x180004d23  call    cs:__imp_GetProcessHeap
0x180004d29  mov     r8d, ebx; dwBytes
0x180004d2c  mov     edx, 8; dwFlags
0x180004d31  mov     rcx, rax; hHeap
0x180004d34  call    cs:__imp_HeapAlloc
0x180004d3a  mov     rbx, rax
0x180004d3d  test    rax, rax
0x180004d40  jnz     loc_180004E37
0x180004d46  mov     rax, cs:WPP_GLOBAL_Control
0x180004d4d  lea     rdi, WPP_GLOBAL_Control
0x180004d54  cmp     rax, rdi
0x180004d57  jnz     loc_180004DFA
0x180004d5d  mov     [r12], rbx
0x180004d61  test    rbx, rbx
0x180004d64  jz      loc_180004F7A
0x180004d6a  mov     byte ptr [r14], 1
0x180004d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d75  cmp     rcx, rdi
0x180004d78  jz      short loc_180004D84
0x180004d7a  test    byte ptr [rcx+6Ch], 8
0x180004d7e  jnz     loc_180004FF6
0x180004d84  mov     eax, ebp
0x180004d86  add     rsp, 48h
0x180004d8a  pop     r15
0x180004d8c  pop     r14
0x180004d8e  pop     r13
0x180004d90  pop     r12
0x180004d92  pop     rdi
0x180004d93  pop     rsi
0x180004d94  pop     rbp
0x180004d95  pop     rbx
0x180004d96  retn
0x180004d97  test    byte ptr [rax+6Ch], 4
0x180004d9b  jnz     loc_180004EFD
0x180004da1  cmp     rax, rcx
0x180004da4  jz      loc_180004CC5
0x180004daa  test    byte ptr [rax+6Ch], 4
0x180004dae  jz      loc_180004CC5
0x180004db4  mov     r9, rdi
0x180004db7  mov     [rsp+88h+var_68], r14
0x180004dbc  mov     r8d, esi
0x180004dbf  lea     rcx, aSyncenumdefaul; "SyncEnumDefaultCreateDirCallback: SyncS"...
0x180004dc6  mov     edx, ebx
0x180004dc8  call    SyncTraceOutputInternal
0x180004dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dd4  mov     r9d, ebx
0x180004dd7  mov     [rsp+88h+var_58], r14
0x180004ddc  mov     [rsp+88h+var_60], rdi
0x180004de1  mov     dword ptr [rsp+88h+var_68], esi
0x180004de5  mov     rcx, [rcx+60h]
0x180004de9  call    WPP_SF_DDqq
0x180004dee  lea     rcx, WPP_GLOBAL_Control
0x180004df5  jmp     loc_180004CC5
0x180004dfa  test    byte ptr [rax+6Ch], 8
0x180004dfe  jz      loc_180004D5D
0x180004e04  mov     rdx, rbx
0x180004e07  lea     rcx, aSyncenumnewcon_0; "SyncEnumNewContext: 0x%p"
0x180004e0e  call    SyncTraceOutputInternal
0x180004e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e1a  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x180004e21  mov     edx, 0Bh
0x180004e26  mov     r9, rbx
0x180004e29  mov     rcx, [rcx+60h]
0x180004e2d  call    WPP_SF_q
0x180004e32  jmp     loc_180004D5D
0x180004e37  mov     rcx, [r15]
0x180004e3a  lea     rdx, [rax+20h]
0x180004e3e  mov     [rax], rcx
0x180004e41  mov     rcx, [r15+10h]
0x180004e45  mov     [rax+8], rcx
0x180004e49  lea     ecx, [rsi-1]
0x180004e4c  mov     [rax+10h], rbp
0x180004e50  mov     [rax+18h], rdx
0x180004e54  mov     eax, 7FFFFFFEh
0x180004e59  mov     r8d, esi
0x180004e5c  cmp     ecx, eax
0x180004e5e  ja      loc_180004EEB
0x180004e64  test    rax, rax
0x180004e67  jz      short loc_180004E85
0x180004e69  movzx   ecx, word ptr [rdi]
0x180004e6c  test    cx, cx
0x180004e6f  jz      short loc_180004E85
0x180004e71  mov     [rdx], cx
0x180004e74  add     rdi, 2
0x180004e78  add     rdx, 2
0x180004e7c  dec     rax
0x180004e7f  sub     r8, 1
0x180004e83  jnz     short loc_180004E64
0x180004e85  test    r8, r8
0x180004e88  lea     rcx, [rdx-2]
0x180004e8c  cmovnz  rcx, rdx
0x180004e90  xor     eax, eax
0x180004e92  mov     [rcx], ax
0x180004e95  jmp     loc_180004D46
0x180004e9a  lea     rdi, WPP_GLOBAL_Control
0x180004ea1  jmp     loc_180004D6E
0x180004ea6  test    byte ptr [rax+6Ch], 4
0x180004eaa  jz      loc_180004CF4
0x180004eb0  mov     r8, rdi
0x180004eb3  lea     rcx, aSyncenumnewcon; "SyncEnumNewContext: ParentDirContext: 0"...
0x180004eba  mov     rdx, r15
0x180004ebd  call    SyncTraceOutputInternal
0x180004ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ec9  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x180004ed0  mov     edx, 0Ah
0x180004ed5  mov     [rsp+88h+var_68], rdi
0x180004eda  mov     r9, r15
0x180004edd  mov     rcx, [rcx+60h]
0x180004ee1  call    WPP_SF_qq
0x180004ee6  jmp     loc_180004CF4
0x180004eeb  test    esi, esi
0x180004eed  jz      loc_180004D46
0x180004ef3  xor     eax, eax
0x180004ef5  mov     [rdx], ax
0x180004ef8  jmp     loc_180004D46
0x180004efd  mov     r8, rdx
0x180004f00  mov     [rsp+88h+var_68], r12
0x180004f05  mov     rdx, r15
0x180004f08  lea     rcx, aSyncenumdefaul_0; "SyncEnumDefaultCreateDirCallback: Ctx: "...
0x180004f0f  mov     r9, r13
0x180004f12  call    SyncTraceOutputInternal
0x180004f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f1e  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x180004f25  mov     rax, [rsp+88h+arg_8]
0x180004f2d  mov     edx, 28h ; '('
0x180004f32  mov     [rsp+88h+var_58], r12
0x180004f37  mov     r9, r15
0x180004f3a  mov     [rsp+88h+var_60], r13
0x180004f3f  mov     rcx, [rcx+60h]
0x180004f43  mov     [rsp+88h+var_68], rax
0x180004f48  call    WPP_SF_qqqq
0x180004f4d  mov     rax, cs:WPP_GLOBAL_Control
0x180004f54  lea     rcx, WPP_GLOBAL_Control
0x180004f5b  jmp     loc_180004DA1
0x180004f60  mov     ecx, esi; Status
0x180004f62  mov     rbx, rax
0x180004f65  call    cs:__imp_RtlNtStatusToDosError
0x180004f6b  mov     [rbx+4], eax
0x180004f6e  lea     rcx, WPP_GLOBAL_Control
0x180004f75  jmp     loc_180004CDB
0x180004f7a  mov     rax, cs:WPP_GLOBAL_Control
0x180004f81  cmp     rax, rdi
0x180004f84  jz      short loc_180004FB4
0x180004f86  test    byte ptr [rax+6Ch], 1
0x180004f8a  jz      short loc_180004FB4
0x180004f8c  lea     rcx, aSyncenumdefaul_6; "SyncEnumDefaultCreateDirCallback: Faile"...
0x180004f93  call    SyncTraceOutputInternal
0x180004f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f9f  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x180004fa6  mov     edx, 2Ah ; '*'
0x180004fab  mov     rcx, [rcx+60h]
0x180004faf  call    WPP_SF_
0x180004fb4  mov     rax, [r15+10h]
0x180004fb8  mov     rbx, [rsp+88h+arg_8]
0x180004fc0  or      dword ptr [rax], 600h
0x180004fc6  mov     rcx, [rbx]; Handle
0x180004fc9  test    rcx, rcx
0x180004fcc  jz      short loc_180004FD6
0x180004fce  call    SyncCloseFile
0x180004fd3  mov     [rbx], rbp
0x180004fd6  mov     rcx, [r13+0]; Handle
0x180004fda  test    rcx, rcx
0x180004fdd  jz      short loc_180004FE8
0x180004fdf  call    SyncCloseFile
0x180004fe4  mov     [r13+0], rbp
0x180004fe8  mov     ebp, 0C000009Ah
0x180004fed  mov     byte ptr [r14], 0
0x180004ff1  jmp     loc_180004D6E
0x180004ff6  mov     edx, ebp
0x180004ff8  lea     rcx, aSyncenumdefaul_5; "SyncEnumDefaultCreateDirCallback: 0x%x"
0x180004fff  call    SyncTraceOutputInternal
0x180005004  mov     rcx, cs:WPP_GLOBAL_Control
0x18000500b  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x180005012  mov     edx, 2Bh ; '+'
0x180005017  mov     r9d, ebp
0x18000501a  mov     rcx, [rcx+60h]
0x18000501e  call    WPP_SF_d
0x180005023  jmp     loc_180004D84
```
