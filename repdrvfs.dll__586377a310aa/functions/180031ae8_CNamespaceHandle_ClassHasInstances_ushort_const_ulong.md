# CNamespaceHandle::ClassHasInstances(ushort const *,ulong)

- ea: `0x180031ae8`
- end: `0x180031c02`
- name: `?ClassHasInstances@CNamespaceHandle@@IEAAJPEBGK@Z`
- size: `282`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180031544`
- `0x180035f1c`

## callees

- `0x1800012b8`
- `0x180006960`
- `0x180023bf0`
- `0x180031ae8`
- `0x180031c08`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031b5e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031bd1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031bee`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031b5e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031bd1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031bee`
- `wbemcomn!GetMemLogObject` at `0x180031b0b`
- `wbemcomn!GetMemLogObject` at `0x180031b7b`
- `wbemcomn!GetMemLogObject` at `0x180031b0b`
- `wbemcomn!GetMemLogObject` at `0x180031b7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031b1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031b8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031b1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031b8b`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ClassHasInstances(CNamespaceHandle *this, const unsigned __int16 *a2)
{
  CMemoryLog *v4; // rax
  unsigned int HasInstancesFromClassHash; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v8; // [rsp+48h] [rbp+20h] BYREF

  CFileName::CFileName((CFileName *)&v8);
  if ( v8 )
  {
    if ( A51Hash(a2, v8) )
    {
      HasInstancesFromClassHash = CNamespaceHandle::ClassHasInstancesFromClassHash(this, v8);
      CWin32DefaultArena::WbemMemFree(v8);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      HasInstancesFromClassHash = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          411,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(v8);
    }
  }
  else
  {
    v4 = GetMemLogObject();
    HasInstancesFromClassHash = -2147217402;
    CMemoryLog::Write(v4, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 410, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
  return HasInstancesFromClassHash;
}

```

## disassembly

```asm
0x180031ae8  mov     [rsp+arg_0], rbx
0x180031aed  push    rsi
0x180031aee  sub     rsp, 20h
0x180031af2  mov     rbx, rdx
0x180031af5  mov     rsi, rcx
0x180031af8  lea     rcx, [rsp+28h+arg_18]; this
0x180031afd  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180031b02  nop
0x180031b03  cmp     [rsp+28h+arg_18], 0
0x180031b09  jnz     short loc_180031B6A
0x180031b0b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180031b11  mov     ebx, 80041006h
0x180031b16  mov     edx, ebx
0x180031b18  mov     rcx, rax
0x180031b1b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180031b21  lea     rax, WPP_GLOBAL_Control
0x180031b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b2f  cmp     rcx, rax
0x180031b32  jz      short loc_180031B5C
0x180031b34  test    byte ptr [rcx+1Ch], 1
0x180031b38  jz      short loc_180031B5C
0x180031b3a  cmp     byte ptr [rcx+19h], 2
0x180031b3e  jb      short loc_180031B5C
0x180031b40  mov     edx, 19Ah
0x180031b45  mov     r9d, 80041006h
0x180031b4b  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180031b52  mov     rcx, [rcx+10h]
0x180031b56  call    WPP_SF_d
0x180031b5b  nop
0x180031b5c  xor     ecx, ecx
0x180031b5e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180031b64  nop
0x180031b65  jmp     loc_180031BF5
0x180031b6a  mov     rdx, [rsp+28h+arg_18]; unsigned __int16 *
0x180031b6f  mov     rcx, rbx; unsigned __int16 *
0x180031b72  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x180031b77  test    al, al
0x180031b79  jnz     short loc_180031BDA
0x180031b7b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180031b81  mov     ebx, 80041006h
0x180031b86  mov     edx, ebx
0x180031b88  mov     rcx, rax
0x180031b8b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180031b91  lea     rax, WPP_GLOBAL_Control
0x180031b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b9f  cmp     rcx, rax
0x180031ba2  jz      short loc_180031BCC
0x180031ba4  test    byte ptr [rcx+1Ch], 1
0x180031ba8  jz      short loc_180031BCC
0x180031baa  cmp     byte ptr [rcx+19h], 2
0x180031bae  jb      short loc_180031BCC
0x180031bb0  mov     edx, 19Bh
0x180031bb5  mov     r9d, 80041006h
0x180031bbb  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180031bc2  mov     rcx, [rcx+10h]
0x180031bc6  call    WPP_SF_d
0x180031bcb  nop
0x180031bcc  mov     rcx, [rsp+28h+arg_18]
0x180031bd1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180031bd7  nop
0x180031bd8  jmp     short loc_180031BF5
0x180031bda  mov     rdx, [rsp+28h+arg_18]; unsigned __int16 *
0x180031bdf  mov     rcx, rsi; this
0x180031be2  call    ?ClassHasInstancesFromClassHash@CNamespaceHandle@@IEAAJPEBG@Z; CNamespaceHandle::ClassHasInstancesFromClassHash(ushort const *)
0x180031be7  mov     ebx, eax
0x180031be9  mov     rcx, [rsp+28h+arg_18]
0x180031bee  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180031bf4  nop
0x180031bf5  mov     eax, ebx
0x180031bf7  mov     rbx, [rsp+28h+arg_0]
0x180031bfc  add     rsp, 20h
0x180031c00  pop     rsi
0x180031c01  retn
```
