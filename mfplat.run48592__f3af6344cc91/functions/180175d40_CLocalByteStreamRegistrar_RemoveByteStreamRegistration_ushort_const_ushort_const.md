# CLocalByteStreamRegistrar::RemoveByteStreamRegistration(ushort const *,ushort const *)

- ea: `0x180175d40`
- end: `0x180175edc`
- name: `?RemoveByteStreamRegistration@CLocalByteStreamRegistrar@@QEAAJPEBG0@Z`
- size: `412`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCWCH lpString1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f63a0`

## callees

- `0x180120030`
- `0x18012158d`
- `0x180175d40`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180175d6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180175d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180175ebb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180175ebb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180175dc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180175e1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180175dc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180175e1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocalByteStreamRegistrar::RemoveByteStreamRegistration(
        LPCRITICAL_SECTION lpCriticalSection,
        LPCWCH lpString1,
        const unsigned __int16 *a3)
{
  const WCHAR *v3; // rbx
  unsigned int v5; // r13d
  int LockCount; // esi
  __int64 i; // rsi
  _RTL_CRITICAL_SECTION_DEBUG *DebugInfo; // r14
  BOOL v9; // r15d
  const WCHAR *v10; // r8
  LPCWCH *v11; // rbx
  BOOL v12; // r12d
  int v13; // ecx
  unsigned int v14; // ecx

  v3 = lpString1;
  v5 = -1072875819;
  EnterCriticalSection(lpCriticalSection);
  LockCount = lpCriticalSection[1].LockCount;
  if ( LockCount )
  {
    for ( i = (unsigned int)(LockCount - 1); (int)i >= 0; v3 = lpString1 )
    {
      DebugInfo = lpCriticalSection[1].DebugInfo;
      if ( v3 || *((_QWORD *)&DebugInfo->Type + 3 * i) )
      {
        v9 = 0;
        if ( v3 )
        {
          v10 = (const WCHAR *)*((_QWORD *)&DebugInfo->Type + 3 * i);
          if ( v10 )
            v9 = CompareStringOrdinal(v3, -1, v10, -1, 1) == 2;
        }
      }
      else
      {
        v9 = 1;
      }
      v11 = (LPCWCH *)(&DebugInfo->CriticalSection + 3 * i);
      if ( a3 || *v11 )
      {
        v12 = 0;
        if ( a3 )
        {
          v11 = (LPCWCH *)(&DebugInfo->CriticalSection + 3 * i);
          if ( *v11 )
            v12 = CompareStringOrdinal(a3, -1, *v11, -1, 1) == 2;
        }
      }
      else
      {
        v12 = 1;
      }
      if ( v9 && v12 )
      {
        operator delete(*((void **)&DebugInfo->Type + 3 * i));
        operator delete((void *)*v11);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&DebugInfo->ProcessLocksList.Flink + 3 * i) + 272LL))(*((_QWORD *)&DebugInfo->ProcessLocksList.Flink + 3 * i));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&DebugInfo->ProcessLocksList.Flink + 3 * i) + 16LL))(*((_QWORD *)&DebugInfo->ProcessLocksList.Flink + 3 * i));
        v13 = lpCriticalSection[1].LockCount;
        if ( v13 && (unsigned int)i <= v13 - 1 )
        {
          v14 = v13 - i - 1;
          if ( v14 )
            memmove_0(
              (char *)lpCriticalSection[1].DebugInfo + 24 * i,
              (char *)lpCriticalSection[1].DebugInfo + 24 * (unsigned int)(i + 1),
              24LL * v14);
          --lpCriticalSection[1].LockCount;
        }
        v5 = 0;
      }
      i = (unsigned int)(i - 1);
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  return v5;
}

```

## disassembly

```asm
0x180175d40  mov     rax, rsp
0x180175d43  mov     [rax+20h], rbx
0x180175d47  mov     [rax+18h], r8
0x180175d4b  mov     [rax+10h], rdx
0x180175d4f  push    rbp
0x180175d50  push    rsi
0x180175d51  push    rdi
0x180175d52  push    r12
0x180175d54  push    r13
0x180175d56  push    r14
0x180175d58  push    r15
0x180175d5a  sub     rsp, 30h
0x180175d5e  mov     rbx, rdx
0x180175d61  mov     rdi, rcx
0x180175d64  mov     r13d, 0C00D36D5h
0x180175d6a  mov     [rax+8], rcx
0x180175d6e  call    cs:__imp_EnterCriticalSection
0x180175d74  nop
0x180175d75  mov     esi, [rdi+30h]
0x180175d78  test    esi, esi
0x180175d7a  jz      loc_180175EB8
0x180175d80  sub     esi, 1
0x180175d83  js      loc_180175EB8
0x180175d89  mov     ecx, 1
0x180175d8e  lea     rbp, [rsi+rsi*2]
0x180175d92  mov     r14, [rdi+28h]
0x180175d96  test    rbx, rbx
0x180175d99  jnz     short loc_180175DA6
0x180175d9b  cmp     [r14+rbp*8], rbx
0x180175d9f  jnz     short loc_180175DA6
0x180175da1  mov     r15d, ecx
0x180175da4  jmp     short loc_180175DD6
0x180175da6  xor     r15d, r15d
0x180175da9  test    rbx, rbx
0x180175dac  jz      short loc_180175DD6
0x180175dae  mov     r8, [r14+rbp*8]; lpString2
0x180175db2  test    r8, r8
0x180175db5  jz      short loc_180175DD6
0x180175db7  mov     [rsp+68h+bIgnoreCase], ecx; bIgnoreCase
0x180175dbb  or      r9d, 0FFFFFFFFh; cchCount2
0x180175dbf  or      edx, r9d; cchCount1
0x180175dc2  mov     rcx, rbx; lpString1
0x180175dc5  call    cs:__imp_CompareStringOrdinal
0x180175dcb  cmp     eax, 2
0x180175dce  lea     ecx, [r15+1]
0x180175dd2  cmovz   r15d, ecx
0x180175dd6  mov     rax, [rsp+68h+lpString1]
0x180175dde  lea     rbx, [r14+8]
0x180175de2  lea     rbx, [rbx+rbp*8]
0x180175de6  test    rax, rax
0x180175de9  jnz     short loc_180175DF5
0x180175deb  cmp     [rbx], rax
0x180175dee  jnz     short loc_180175DF5
0x180175df0  mov     r12d, ecx
0x180175df3  jmp     short loc_180175E2A
0x180175df5  xor     r12d, r12d
0x180175df8  test    rax, rax
0x180175dfb  jz      short loc_180175E2A
0x180175dfd  lea     rbx, [r14+8]
0x180175e01  lea     rbx, [rbx+rbp*8]
0x180175e05  mov     r8, [rbx]; lpString2
0x180175e08  test    r8, r8
0x180175e0b  jz      short loc_180175E2A
0x180175e0d  mov     [rsp+68h+bIgnoreCase], ecx; bIgnoreCase
0x180175e11  or      r9d, 0FFFFFFFFh; cchCount2
0x180175e15  or      edx, r9d; cchCount1
0x180175e18  mov     rcx, rax; lpString1
0x180175e1b  call    cs:__imp_CompareStringOrdinal
0x180175e21  cmp     eax, 2
0x180175e24  jnz     short loc_180175E2A
0x180175e26  lea     r12d, [rax-1]
0x180175e2a  test    r15d, r15d
0x180175e2d  jz      short loc_180175EA6
0x180175e2f  test    r12d, r12d
0x180175e32  jz      short loc_180175EA6
0x180175e34  mov     rcx, [r14+rbp*8]; void *
0x180175e38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180175e3d  mov     rcx, [rbx]; void *
0x180175e40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180175e45  mov     rcx, [r14+rbp*8+10h]
0x180175e4a  mov     rax, [rcx]
0x180175e4d  mov     rax, [rax+110h]
0x180175e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175e59  mov     rcx, [r14+rbp*8+10h]
0x180175e5e  mov     rax, [rcx]
0x180175e61  mov     rax, [rax+10h]
0x180175e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180175e6a  mov     ecx, [rdi+30h]
0x180175e6d  cmp     ecx, 1
0x180175e70  jb      short loc_180175EA3
0x180175e72  lea     eax, [rcx-1]
0x180175e75  cmp     esi, eax
0x180175e77  ja      short loc_180175EA3
0x180175e79  sub     ecx, esi
0x180175e7b  sub     ecx, 1
0x180175e7e  jz      short loc_180175EA0
0x180175e80  mov     r9, [rdi+28h]
0x180175e84  lea     r8, [rcx+rcx*2]
0x180175e88  shl     r8, 3; Size
0x180175e8c  lea     eax, [rsi+1]
0x180175e8f  lea     rax, [rax+rax*2]
0x180175e93  lea     rdx, [r9+rax*8]; Src
0x180175e97  lea     rcx, [r9+rbp*8]; void *
0x180175e9b  call    memmove_0
0x180175ea0  dec     dword ptr [rdi+30h]
0x180175ea3  xor     r13d, r13d
0x180175ea6  mov     ecx, 1
0x180175eab  sub     esi, ecx
0x180175ead  mov     rbx, [rsp+68h+arg_8]
0x180175eb2  jns     loc_180175D8E
0x180175eb8  mov     rcx, rdi; lpCriticalSection
0x180175ebb  call    cs:__imp_LeaveCriticalSection
0x180175ec1  mov     eax, r13d
0x180175ec4  mov     rbx, [rsp+68h+arg_18]
0x180175ecc  add     rsp, 30h
0x180175ed0  pop     r15
0x180175ed2  pop     r14
0x180175ed4  pop     r13
0x180175ed6  pop     r12
0x180175ed8  pop     rdi
0x180175ed9  pop     rsi
0x180175eda  pop     rbp
0x180175edb  retn
```
