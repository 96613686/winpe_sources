# IDriverClose

- ea: `0x180001e60`
- end: `0x180001f7c`
- name: `IDriverClose`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f90`
- `0x180002400`
- `0x180002e70`
- `0x180005530`

## callees

- `0x1800018e0`
- `0x180001e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ef1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ef1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001efb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001efb`
- `api-ms-win-mm-misc-l1-1-0!CloseDriver` at `0x180001ecb`
- `api-ms-win-mm-misc-l1-1-0!CloseDriver` at `0x180001ecb`

## pseudocode

```c
__int64 __fastcall IDriverClose(__int64 a1, int a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  HDRVR v5; // rcx
  LRESULT v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rcx

  if ( !a1 )
    return 5;
  if ( a2 )
    return 10;
  v3 = *(_QWORD *)(a1 + 20);
  v4 = *(_QWORD *)(v3 + 4);
  if ( *(_QWORD *)(a1 + 12) && *(_QWORD *)(v4 + 112) != a1 )
    return 513;
  v5 = *(HDRVR *)(a1 + 40);
  if ( v5 || *(_QWORD *)(a1 + 56) )
  {
    if ( *(_QWORD *)(a1 + 48) )
    {
      v7 = IDriverMessage(a1, 4, 0, 0);
    }
    else
    {
      if ( !v5 )
        goto LABEL_7;
      v7 = CloseDriver(v5, 0, 0);
    }
    if ( v7 )
      goto LABEL_11;
LABEL_7:
    if ( *(_QWORD *)(v4 + 112) != a1 )
      return 1;
  }
LABEL_11:
  v8 = *(_QWORD *)(v3 + 28);
  if ( a1 == v8 )
  {
    *(_QWORD *)(v3 + 28) = *(_QWORD *)(a1 + 4);
LABEL_13:
    *(_DWORD *)a1 = 666;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 - 40));
    LocalFree((HLOCAL)(a1 - 40));
    return 0;
  }
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = (_QWORD *)(v8 + 4);
      v8 = *(_QWORD *)(v8 + 4);
      if ( a1 == v8 )
        break;
      if ( !v8 )
        return 5;
    }
    *v9 = *(_QWORD *)(a1 + 4);
    goto LABEL_13;
  }
  return 5;
}

```

## disassembly

```asm
0x180001e60  mov     [rsp+arg_0], rbx
0x180001e65  mov     [rsp+arg_8], rsi
0x180001e6a  push    rdi
0x180001e6b  sub     rsp, 20h
0x180001e6f  mov     rbx, rcx
0x180001e72  test    rcx, rcx
0x180001e75  jz      loc_180001F66
0x180001e7b  test    edx, edx
0x180001e7d  jnz     loc_180001F31
0x180001e83  cmp     qword ptr [rcx+0Ch], 0
0x180001e88  mov     rsi, [rcx+14h]
0x180001e8c  mov     rdi, [rsi+4]
0x180001e90  jnz     loc_180001F3B
0x180001e96  mov     rcx, [rcx+28h]; hDriver
0x180001e9a  test    rcx, rcx
0x180001e9d  jz      short loc_180001F13
0x180001e9f  cmp     qword ptr [rbx+30h], 0
0x180001ea4  jnz     short loc_180001F1C
0x180001ea6  test    rcx, rcx
0x180001ea9  jnz     short loc_180001EC6
0x180001eab  cmp     [rdi+70h], rbx
0x180001eaf  jz      short loc_180001ED6
0x180001eb1  mov     eax, 1
0x180001eb6  mov     rbx, [rsp+28h+arg_0]
0x180001ebb  mov     rsi, [rsp+28h+arg_8]
0x180001ec0  add     rsp, 20h
0x180001ec4  pop     rdi
0x180001ec5  retn
0x180001ec6  xor     r8d, r8d; lParam2
0x180001ec9  xor     edx, edx; lParam1
0x180001ecb  call    cs:__imp_CloseDriver
0x180001ed1  test    rax, rax
0x180001ed4  jz      short loc_180001EAB
0x180001ed6  mov     rax, [rsi+1Ch]
0x180001eda  cmp     rbx, rax
0x180001edd  jnz     short loc_180001F4F
0x180001edf  mov     rax, [rbx+4]
0x180001ee3  mov     [rsi+1Ch], rax
0x180001ee7  lea     rcx, [rbx-28h]; lpCriticalSection
0x180001eeb  mov     dword ptr [rbx], 29Ah
0x180001ef1  call    cs:__imp_DeleteCriticalSection
0x180001ef7  lea     rcx, [rbx-28h]; hMem
0x180001efb  call    cs:__imp_LocalFree
0x180001f01  mov     rbx, [rsp+28h+arg_0]
0x180001f06  xor     eax, eax
0x180001f08  mov     rsi, [rsp+28h+arg_8]
0x180001f0d  add     rsp, 20h
0x180001f11  pop     rdi
0x180001f12  retn
0x180001f13  cmp     qword ptr [rbx+38h], 0
0x180001f18  jnz     short loc_180001E9F
0x180001f1a  jmp     short loc_180001ED6
0x180001f1c  xor     r9d, r9d
0x180001f1f  xor     r8d, r8d
0x180001f22  mov     edx, 4
0x180001f27  mov     rcx, rbx
0x180001f2a  call    IDriverMessage
0x180001f2f  jmp     short loc_180001ED1
0x180001f31  mov     eax, 0Ah
0x180001f36  jmp     loc_180001EB6
0x180001f3b  cmp     [rdi+70h], rbx
0x180001f3f  jz      loc_180001E96
0x180001f45  mov     eax, 201h
0x180001f4a  jmp     loc_180001EB6
0x180001f4f  test    rax, rax
0x180001f52  jz      short loc_180001F66
0x180001f54  lea     rcx, [rax+4]
0x180001f58  mov     rax, [rax+4]
0x180001f5c  cmp     rbx, rax
0x180001f5f  jz      short loc_180001F70
0x180001f61  test    rax, rax
0x180001f64  jnz     short loc_180001F54
0x180001f66  mov     eax, 5
0x180001f6b  jmp     loc_180001EB6
0x180001f70  mov     rax, [rbx+4]
0x180001f74  mov     [rcx], rax
0x180001f77  jmp     loc_180001EE7
```
