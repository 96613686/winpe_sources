# SpGetExtendedInformation

- ea: `0x18004a110`
- end: `0x18004a1ae`
- name: `SpGetExtendedInformation`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180014404`
- `0x18004a110`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004a165`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004a165`

## string_xrefs

- `0x18004a15e`: `%SystemRoot%\SysWOW64\msv1_0.DLL`

## pseudocode

```c
__int64 __fastcall SpGetExtendedInformation(int a1, __int64 *a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int16 v6; // ax
  _DWORD *LsaHeap; // rax

  v2 = 0;
  if ( a1 == 2 )
  {
    LsaHeap = (_DWORD *)NtLmAllocateLsaHeap(60);
    if ( LsaHeap )
    {
      *LsaHeap = 2;
      LsaHeap[2] = 2;
      LsaHeap[3] = 16;
      LsaHeap[4] = 30;
      *a2 = (__int64)LsaHeap;
      return v2;
    }
    return (unsigned int)-1073741670;
  }
  if ( a1 == 4 )
  {
    v4 = NtLmAllocateLsaHeap(576);
    v5 = v4;
    if ( v4 )
    {
      *(_DWORD *)v4 = 4;
      *(_QWORD *)(v4 + 16) = v4 + 56;
      v6 = 2 * ExpandEnvironmentStringsW(L"%SystemRoot%\\SysWOW64\\msv1_0.DLL", (LPWSTR)(v4 + 56), 0x104u);
      *(_WORD *)(v5 + 8) = v6;
      *(_WORD *)(v5 + 10) = v6 + 2;
      *a2 = v5;
      return v2;
    }
    return (unsigned int)-1073741670;
  }
  return (unsigned int)-2146893054;
}

```

## disassembly

```asm
0x18004a110  push    rbx
0x18004a112  push    rbp
0x18004a113  push    rsi
0x18004a114  push    rdi
0x18004a115  sub     rsp, 28h
0x18004a119  xor     ebx, ebx
0x18004a11b  mov     rsi, rdx
0x18004a11e  lea     ebp, [rbx+2]
0x18004a121  cmp     ecx, ebp
0x18004a123  jz      short loc_18004A17E
0x18004a125  cmp     ecx, 4
0x18004a128  jz      short loc_18004A131
0x18004a12a  mov     ebx, 80090302h
0x18004a12f  jmp     short loc_18004A1A3
0x18004a131  mov     ecx, 240h
0x18004a136  call    NtLmAllocateLsaHeap
0x18004a13b  mov     rdi, rax
0x18004a13e  test    rax, rax
0x18004a141  jnz     short loc_18004A14A
0x18004a143  mov     ebx, 0C000009Ah
0x18004a148  jmp     short loc_18004A1A3
0x18004a14a  lea     rdx, [rax+38h]; lpDst
0x18004a14e  mov     dword ptr [rax], 4
0x18004a154  mov     r8d, 104h; nSize
0x18004a15a  mov     [rax+10h], rdx
0x18004a15e  lea     rcx, aSystemrootSysw; "%SystemRoot%\\SysWOW64\\msv1_0.DLL"
0x18004a165  call    cs:__imp_ExpandEnvironmentStringsW
0x18004a16b  add     ax, ax
0x18004a16e  mov     [rdi+8], ax
0x18004a172  add     ax, bp
0x18004a175  mov     [rdi+0Ah], ax
0x18004a179  mov     [rsi], rdi
0x18004a17c  jmp     short loc_18004A1A3
0x18004a17e  mov     ecx, 3Ch ; '<'
0x18004a183  call    NtLmAllocateLsaHeap
0x18004a188  test    rax, rax
0x18004a18b  jz      short loc_18004A143
0x18004a18d  mov     [rax], ebp
0x18004a18f  mov     [rax+8], ebp
0x18004a192  mov     dword ptr [rax+0Ch], 10h
0x18004a199  mov     dword ptr [rax+10h], 1Eh
0x18004a1a0  mov     [rsi], rax
0x18004a1a3  mov     eax, ebx
0x18004a1a5  add     rsp, 28h
0x18004a1a9  pop     rdi
0x18004a1aa  pop     rsi
0x18004a1ab  pop     rbp
0x18004a1ac  pop     rbx
0x18004a1ad  retn
```
