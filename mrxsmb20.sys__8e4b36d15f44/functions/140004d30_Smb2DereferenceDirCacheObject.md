# Smb2DereferenceDirCacheObject

- ea: `0x140004d30`
- end: `0x140004f13`
- name: `Smb2DereferenceDirCacheObject`
- size: `483`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b80`
- `0x140003570`
- `0x140004640`
- `0x140004940`
- `0x140005800`
- `0x140005820`
- `0x140012f00`
- `0x140014a00`
- `0x140014db0`
- `0x140015780`

## callees

- `0x140004d30`
- `0x14002d630`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004e67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ebb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ed7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ebb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ed7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004eef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004e21`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004e21`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004ddc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004ddc`
- `rdbss!RxTearDownDiagnosticLogger` at `0x140004e31`
- `rdbss!RxTearDownDiagnosticLogger` at `0x140004e31`
- `rdbss!RxDiagnosticTrace` at `0x140004da6`
- `rdbss!RxDiagnosticTrace` at `0x140004da6`

## pseudocode

```c
void __fastcall Smb2DereferenceDirCacheObject(char *P)
{
  signed __int32 v2; // edi
  signed __int32 v3; // eax
  char **v4; // r8
  PVOID *v5; // rdx
  unsigned int i; // edi
  char *v7; // rsi
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)P + 9, 1u) - 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids, P, v2 + 1, v2);
  }
  RxDiagnosticTrace(*((_QWORD *)P + 1), 8, "Deref %d --> %d", (unsigned int)(v2 + 1));
  v3 = _InterlockedExchangeAdd((volatile signed __int32 *)P + 9, 0xFFFFFFFE) - 2;
  if ( v3 >= 0 )
  {
    if ( !v3 )
    {
      ExAcquirePushLockExclusiveEx(&GlobalDirCacheObjectListLock, 0);
      v4 = (char **)*((_QWORD *)P + 2);
      if ( v4[1] != P + 16 || (v5 = (PVOID *)*((_QWORD *)P + 3), *v5 != P + 16) )
        __fastfail(3u);
      *v5 = v4;
      v4[1] = (char *)v5;
      ExReleasePushLockExclusiveEx(&GlobalDirCacheObjectListLock, 0);
      RxTearDownDiagnosticLogger(*((_QWORD *)P + 1));
      *((_QWORD *)P + 1) = 170;
      for ( i = 0; i < 8; ++i )
      {
        v7 = &P[8 * i];
        v8 = (void *)*((_QWORD *)v7 + 19);
        if ( !v8 )
          break;
        ExFreePoolWithTag(v8, 0x6D536344u);
        *((_QWORD *)v7 + 19) = 0;
      }
      v9 = (void *)*((_QWORD *)P + 17);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0x6D536344u);
        *((_QWORD *)P + 17) = 0;
      }
      v10 = (void *)*((_QWORD *)P + 18);
      if ( v10 )
      {
        ExFreePoolWithTag(v10, 0x6D536344u);
        *((_QWORD *)P + 18) = 0;
      }
      ExFreePoolWithTag(*((PVOID *)P + 14), 0x6D536344u);
      *((_QWORD *)P + 14) = 0;
      ExFreePoolWithTag(P, 0x6D536344u);
    }
  }
  else
  {
    __int2c();
  }
}

```

## disassembly

```asm
0x140004d30  mov     [rsp+arg_10], rbx
0x140004d35  push    rdi
0x140004d36  sub     rsp, 30h
0x140004d3a  mov     rbx, rcx
0x140004d3d  mov     edi, 1
0x140004d42  lock xadd [rcx+24h], edi
0x140004d47  dec     edi
0x140004d49  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004d50  lea     rax, WPP_GLOBAL_Control
0x140004d57  cmp     rcx, rax
0x140004d5a  jz      short loc_140004D8E
0x140004d5c  test    dword ptr [rcx+2Ch], 100h
0x140004d63  jz      short loc_140004D8E
0x140004d65  cmp     byte ptr [rcx+29h], 4
0x140004d69  jb      short loc_140004D8E
0x140004d6b  mov     rcx, [rcx+18h]
0x140004d6f  lea     eax, [rdi+1]
0x140004d72  mov     edx, 0Ah
0x140004d77  mov     [rsp+38h+var_10], edi
0x140004d7b  mov     r9, rbx
0x140004d7e  mov     [rsp+38h+var_18], eax
0x140004d82  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140004d89  call    WPP_SF_qdd
0x140004d8e  mov     rcx, [rbx+8]
0x140004d92  lea     r9d, [rdi+1]
0x140004d96  lea     r8, aDerefDD; "Deref %d --> %d"
0x140004d9d  mov     [rsp+38h+var_18], edi
0x140004da1  mov     edx, 8
0x140004da6  call    cs:__imp_RxDiagnosticTrace
0x140004dad  nop     dword ptr [rax+rax+00h]
0x140004db2  mov     eax, 0FFFFFFFEh
0x140004db7  lock xadd [rbx+24h], eax
0x140004dbc  add     eax, 0FFFFFFFEh
0x140004dbf  jns     short loc_140004DCF
0x140004dc1  int     2Ch; Windows NT - assertion failure
0x140004dc3  mov     rbx, [rsp+38h+arg_10]
0x140004dc8  add     rsp, 30h
0x140004dcc  pop     rdi
0x140004dcd  retn
0x140004dcf  test    eax, eax
0x140004dd1  jnz     short loc_140004DC3
0x140004dd3  xor     edx, edx
0x140004dd5  lea     rcx, GlobalDirCacheObjectListLock
0x140004ddc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140004de3  nop     dword ptr [rax+rax+00h]
0x140004de8  mov     r8, [rbx+10h]
0x140004dec  lea     rax, [rbx+10h]
0x140004df0  cmp     [r8+8], rax
0x140004df4  jnz     loc_140004F0C
0x140004dfa  mov     rdx, [rax+8]
0x140004dfe  cmp     [rdx], rax
0x140004e01  jnz     loc_140004F0C
0x140004e07  mov     [rdx], r8
0x140004e0a  lea     rcx, GlobalDirCacheObjectListLock
0x140004e11  mov     [r8+8], rdx
0x140004e15  xor     edx, edx
0x140004e17  mov     [rsp+38h+arg_0], rbp
0x140004e1c  mov     [rsp+38h+arg_8], rsi
0x140004e21  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140004e28  nop     dword ptr [rax+rax+00h]
0x140004e2d  mov     rcx, [rbx+8]
0x140004e31  call    cs:__imp_RxTearDownDiagnosticLogger
0x140004e38  nop     dword ptr [rax+rax+00h]
0x140004e3d  xor     ebp, ebp
0x140004e3f  mov     qword ptr [rbx+8], 0AAh
0x140004e47  mov     edi, ebp
0x140004e49  nop     dword ptr [rax+00000000h]
0x140004e50  mov     eax, edi
0x140004e52  lea     rsi, [rbx+rax*8]
0x140004e56  mov     rcx, [rsi+98h]; P
0x140004e5d  test    rcx, rcx
0x140004e60  jz      short loc_140004E81
0x140004e62  mov     edx, 6D536344h; Tag
0x140004e67  call    cs:__imp_ExFreePoolWithTag
0x140004e6e  nop     dword ptr [rax+rax+00h]
0x140004e73  inc     edi
0x140004e75  mov     [rsi+98h], rbp
0x140004e7c  cmp     edi, 8
0x140004e7f  jb      short loc_140004E50
0x140004e81  mov     rcx, [rbx+88h]; P
0x140004e88  mov     rsi, [rsp+38h+arg_8]
0x140004e8d  test    rcx, rcx
0x140004e90  jz      short loc_140004EAA
0x140004e92  mov     edx, 6D536344h; Tag
0x140004e97  call    cs:__imp_ExFreePoolWithTag
0x140004e9e  nop     dword ptr [rax+rax+00h]
0x140004ea3  mov     [rbx+88h], rbp
0x140004eaa  mov     rcx, [rbx+90h]; P
0x140004eb1  test    rcx, rcx
0x140004eb4  jz      short loc_140004ECE
0x140004eb6  mov     edx, 6D536344h; Tag
0x140004ebb  call    cs:__imp_ExFreePoolWithTag
0x140004ec2  nop     dword ptr [rax+rax+00h]
0x140004ec7  mov     [rbx+90h], rbp
0x140004ece  mov     rcx, [rbx+70h]; P
0x140004ed2  mov     edx, 6D536344h; Tag
0x140004ed7  call    cs:__imp_ExFreePoolWithTag
0x140004ede  nop     dword ptr [rax+rax+00h]
0x140004ee3  mov     edx, 6D536344h; Tag
0x140004ee8  mov     [rbx+70h], rbp
0x140004eec  mov     rcx, rbx; P
0x140004eef  call    cs:__imp_ExFreePoolWithTag
0x140004ef6  nop     dword ptr [rax+rax+00h]
0x140004efb  mov     rbp, [rsp+38h+arg_0]
0x140004f00  mov     rbx, [rsp+38h+arg_10]
0x140004f05  add     rsp, 30h
0x140004f09  pop     rdi
0x140004f0a  retn
0x140004f0c  mov     ecx, 3
0x140004f11  int     29h; Win8: RtlFailFast(ecx)
```
