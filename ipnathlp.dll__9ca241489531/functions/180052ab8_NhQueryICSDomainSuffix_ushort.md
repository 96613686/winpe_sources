# NhQueryICSDomainSuffix(ushort * *)

- ea: `0x180052ab8`
- end: `0x180052f33`
- name: `?NhQueryICSDomainSuffix@@YAJPEAPEAG@Z`
- size: `1147`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007c140`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180034eb8`
- `0x180035f20`
- `0x180052ab8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052cca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052cca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052cbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052e5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052cbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052e5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052cd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052d94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052dad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052cd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052d94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052dad`
- `ntdll!RtlInitUnicodeString` at `0x180052ba8`
- `ntdll!RtlInitUnicodeString` at `0x180052ba8`
- `ntdll!NtOpenKey` at `0x180052bdd`
- `ntdll!NtOpenKey` at `0x180052bdd`
- `ntdll!NtClose` at `0x180052c61`
- `ntdll!NtClose` at `0x180052c61`

## string_xrefs

- `0x180052b9a`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall NhQueryICSDomainSuffix(unsigned __int16 **a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  NTSTATUS v6; // eax
  int ValueKey; // ebx
  unsigned __int16 *v8; // rdi
  __int64 v9; // rax
  unsigned __int64 v10; // r15
  HANDLE v11; // rax
  unsigned __int16 *v12; // rax
  HANDLE v13; // rax
  PVOID *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  HANDLE v17; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  unsigned __int16 *v20; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+48h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  lpMem = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !a1 )
  {
    v3 = -1073741811;
    if ( v2 == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    {
      WPP_SF_d(v2[2], 82, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, 3221225485LL);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 6u )
      return v3;
    v4 = 83;
LABEL_14:
    WPP_SF_d(v2[2], v4, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, v3);
    return v3;
  }
  *a1 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v3 = v6;
  if ( v6 < 0 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
        (unsigned int)v6);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 6u )
      return v3;
    v4 = 85;
    goto LABEL_14;
  }
  ValueKey = NhQueryValueKey(KeyHandle, L"ICSDomain", (struct _KEY_VALUE_PARTIAL_INFORMATION **)&lpMem);
  NtClose(KeyHandle);
  if ( ValueKey >= 0 && (v8 = (unsigned __int16 *)lpMem) != 0 )
  {
    if ( *((_DWORD *)lpMem + 1) != 1 || *(_WORD *)((char *)lpMem + *((unsigned int *)lpMem + 2) + 10) )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      v3 = -1073741823;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
          3221225473LL);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 6u )
        return v3;
      v4 = 90;
      goto LABEL_14;
    }
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)lpMem + v9 + 6) );
    v10 = (unsigned int)(v9 + 1);
    v11 = GetProcessHeap();
    v12 = (unsigned __int16 *)HeapAlloc(v11, 8u, 2 * v10);
    *a1 = v12;
    if ( !v12 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v8);
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 3221225495LL;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          91,
          &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
          3221225495LL);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 8) == 0 || *((_BYTE *)v14 + 25) < 6u )
        return 3221225495LL;
      v15 = 92;
LABEL_67:
      WPP_SF_d(v14[2], v15, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, 3221225495LL);
      return 3221225495LL;
    }
    v16 = StringCchCopyW(v12, v10, v8 + 6);
    if ( v16 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
        (unsigned int)v16);
    }
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v8);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
        (unsigned int)ValueKey);
    }
    v19 = GetProcessHeap();
    v20 = (unsigned __int16 *)HeapAlloc(v19, 8u, 0x16u);
    *a1 = v20;
    if ( !v20 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 3221225495LL;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
          3221225495LL);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 8) == 0 || *((_BYTE *)v14 + 25) < 6u )
        return 3221225495LL;
      v15 = 88;
      goto LABEL_67;
    }
    StringCchCopyW(v20, 0xBu, L"mshome.net");
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180052ab8  mov     [rsp-38h+arg_10], rbx
0x180052abd  push    rbp
0x180052abe  push    rsi
0x180052abf  push    rdi
0x180052ac0  push    r12
0x180052ac2  push    r13
0x180052ac4  push    r14
0x180052ac6  push    r15
0x180052ac8  mov     rbp, rsp
0x180052acb  sub     rsp, 60h
0x180052acf  mov     r14, rcx
0x180052ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ad9  lea     r13, WPP_GLOBAL_Control
0x180052ae0  mov     r12d, 8
0x180052ae6  cmp     rcx, r13
0x180052ae9  jz      short loc_180052B13
0x180052aeb  test    [rcx+1Ch], r12b
0x180052aef  jz      short loc_180052B13
0x180052af1  cmp     byte ptr [rcx+19h], 6
0x180052af5  jb      short loc_180052B13
0x180052af7  mov     rcx, [rcx+10h]
0x180052afb  lea     edx, [r12+49h]
0x180052b00  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052b07  call    WPP_SF_
0x180052b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b13  xorps   xmm0, xmm0
0x180052b16  xor     r15d, r15d
0x180052b19  mov     [rbp+lpMem], r15
0x180052b1d  mov     [rbp+KeyHandle], r15
0x180052b21  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180052b25  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180052b29  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180052b2d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180052b31  test    r14, r14
0x180052b34  jnz     short loc_180052B9A
0x180052b36  mov     ebx, 0C000000Dh
0x180052b3b  cmp     rcx, r13
0x180052b3e  jz      short loc_180052B93
0x180052b40  test    [rcx+1Ch], r12b
0x180052b44  jz      short loc_180052B6A
0x180052b46  cmp     byte ptr [rcx+19h], 2
0x180052b4a  jb      short loc_180052B6A
0x180052b4c  mov     rcx, [rcx+10h]
0x180052b50  lea     edx, [r15+52h]
0x180052b54  mov     r9d, ebx
0x180052b57  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052b5e  call    WPP_SF_d
0x180052b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b6a  cmp     rcx, r13
0x180052b6d  jz      short loc_180052B93
0x180052b6f  test    [rcx+1Ch], r12b
0x180052b73  jz      short loc_180052B93
0x180052b75  cmp     byte ptr [rcx+19h], 6
0x180052b79  jb      short loc_180052B93
0x180052b7b  mov     edx, 53h ; 'S'
0x180052b80  mov     rcx, [rcx+10h]
0x180052b84  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052b8b  mov     r9d, ebx
0x180052b8e  call    WPP_SF_d
0x180052b93  mov     eax, ebx
0x180052b95  jmp     loc_180052F1B
0x180052b9a  lea     rdx, ?NhTcpipParametersString@@3QBGB; "\\Registry\\Machine\\System\\CurrentCon"...
0x180052ba1  mov     [r14], r15
0x180052ba4  lea     rcx, [rbp+DestinationString]; DestinationString
0x180052ba8  call    cs:__imp_RtlInitUnicodeString
0x180052bae  lea     rax, [rbp+DestinationString]
0x180052bb2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180052bb9  xorps   xmm0, xmm0
0x180052bbc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180052bc0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180052bc4  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x180052bc8  mov     edx, 20019h; DesiredAccess
0x180052bcd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180052bd4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180052bd8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180052bdd  call    cs:__imp_NtOpenKey
0x180052be3  mov     ebx, eax
0x180052be5  test    eax, eax
0x180052be7  jns     short loc_180052C47
0x180052be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bf0  cmp     rcx, r13
0x180052bf3  jz      short loc_180052B93
0x180052bf5  test    [rcx+1Ch], r12b
0x180052bf9  jz      short loc_180052C20
0x180052bfb  cmp     byte ptr [rcx+19h], 2
0x180052bff  jb      short loc_180052C20
0x180052c01  mov     rcx, [rcx+10h]
0x180052c05  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052c0c  mov     edx, 54h ; 'T'
0x180052c11  mov     r9d, eax
0x180052c14  call    WPP_SF_d
0x180052c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c20  cmp     rcx, r13
0x180052c23  jz      loc_180052B93
0x180052c29  test    [rcx+1Ch], r12b
0x180052c2d  jz      loc_180052B93
0x180052c33  cmp     byte ptr [rcx+19h], 6
0x180052c37  jb      loc_180052B93
0x180052c3d  mov     edx, 55h ; 'U'
0x180052c42  jmp     loc_180052B80
0x180052c47  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180052c4b  lea     r8, [rbp+lpMem]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180052c4f  lea     rdx, aIcsdomain_0; "ICSDomain"
0x180052c56  call    ?NhQueryValueKey@@YAJPEAXQEBGPEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@@Z; NhQueryValueKey(void *,ushort const * const,_KEY_VALUE_PARTIAL_INFORMATION * *)
0x180052c5b  mov     rcx, [rbp+KeyHandle]; Handle
0x180052c5f  mov     ebx, eax
0x180052c61  call    cs:__imp_NtClose
0x180052c67  test    ebx, ebx
0x180052c69  js      loc_180052E1A
0x180052c6f  mov     rdi, [rbp+lpMem]
0x180052c73  test    rdi, rdi
0x180052c76  jz      loc_180052E1A
0x180052c7c  cmp     dword ptr [rdi+4], 1
0x180052c80  jnz     loc_180052D9F
0x180052c86  mov     ecx, [rdi+8]
0x180052c89  cmp     r15w, [rcx+rdi+0Ah]
0x180052c8f  jnz     loc_180052D9F
0x180052c95  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052c99  inc     rax
0x180052c9c  cmp     [rdi+rax*2+0Ch], r15w
0x180052ca2  jnz     short loc_180052C99
0x180052ca4  inc     eax
0x180052ca6  mov     r15d, eax
0x180052ca9  lea     rbx, [rax+rax]
0x180052cad  call    cs:__imp_GetProcessHeap
0x180052cb3  mov     r8, rbx; dwBytes
0x180052cb6  mov     edx, r12d; dwFlags
0x180052cb9  mov     rcx, rax; hHeap
0x180052cbc  call    cs:__imp_HeapAlloc
0x180052cc2  mov     [r14], rax
0x180052cc5  test    rax, rax
0x180052cc8  jnz     short loc_180052D43
0x180052cca  call    cs:__imp_GetProcessHeap
0x180052cd0  mov     r8, rdi; lpMem
0x180052cd3  xor     edx, edx; dwFlags
0x180052cd5  mov     rcx, rax; hHeap
0x180052cd8  call    cs:__imp_HeapFree
0x180052cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ce5  cmp     rcx, r13
0x180052ce8  jz      loc_180052ECE
0x180052cee  test    [rcx+1Ch], r12b
0x180052cf2  jz      short loc_180052D1C
0x180052cf4  cmp     byte ptr [rcx+19h], 2
0x180052cf8  jb      short loc_180052D1C
0x180052cfa  mov     rcx, [rcx+10h]
0x180052cfe  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052d05  mov     edx, 5Bh ; '['
0x180052d0a  mov     r9d, 0C0000017h
0x180052d10  call    WPP_SF_d
0x180052d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d1c  cmp     rcx, r13
0x180052d1f  jz      loc_180052ECE
0x180052d25  test    [rcx+1Ch], r12b
0x180052d29  jz      loc_180052ECE
0x180052d2f  cmp     byte ptr [rcx+19h], 6
0x180052d33  jb      loc_180052ECE
0x180052d39  mov     edx, 5Ch ; '\'
0x180052d3e  jmp     loc_180052EB8
0x180052d43  lea     r8, [rdi+0Ch]; unsigned __int16 *
0x180052d47  mov     rdx, r15; unsigned __int64
0x180052d4a  mov     rcx, rax; unsigned __int16 *
0x180052d4d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052d52  test    eax, eax
0x180052d54  jns     short loc_180052D86
0x180052d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d5d  cmp     rcx, r13
0x180052d60  jz      short loc_180052D86
0x180052d62  test    [rcx+1Ch], r12b
0x180052d66  jz      short loc_180052D86
0x180052d68  cmp     byte ptr [rcx+19h], 2
0x180052d6c  jb      short loc_180052D86
0x180052d6e  mov     rcx, [rcx+10h]
0x180052d72  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052d79  mov     edx, 5Dh ; ']'
0x180052d7e  mov     r9d, eax
0x180052d81  call    WPP_SF_d
0x180052d86  call    cs:__imp_GetProcessHeap
0x180052d8c  mov     r8, rdi; lpMem
0x180052d8f  xor     edx, edx; dwFlags
0x180052d91  mov     rcx, rax; hHeap
0x180052d94  call    cs:__imp_HeapFree
0x180052d9a  jmp     loc_180052EE9
0x180052d9f  call    cs:__imp_GetProcessHeap
0x180052da5  mov     r8, rdi; lpMem
0x180052da8  xor     edx, edx; dwFlags
0x180052daa  mov     rcx, rax; hHeap
0x180052dad  call    cs:__imp_HeapFree
0x180052db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180052dba  mov     ebx, 0C0000001h
0x180052dbf  cmp     rcx, r13
0x180052dc2  jz      loc_180052B93
0x180052dc8  test    [rcx+1Ch], r12b
0x180052dcc  jz      short loc_180052DF3
0x180052dce  cmp     byte ptr [rcx+19h], 2
0x180052dd2  jb      short loc_180052DF3
0x180052dd4  mov     rcx, [rcx+10h]
0x180052dd8  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052ddf  mov     edx, 59h ; 'Y'
0x180052de4  mov     r9d, ebx
0x180052de7  call    WPP_SF_d
0x180052dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180052df3  cmp     rcx, r13
0x180052df6  jz      loc_180052B93
0x180052dfc  test    [rcx+1Ch], r12b
0x180052e00  jz      loc_180052B93
0x180052e06  cmp     byte ptr [rcx+19h], 6
0x180052e0a  jb      loc_180052B93
0x180052e10  mov     edx, 5Ah ; 'Z'
0x180052e15  jmp     loc_180052B80
0x180052e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e21  cmp     rcx, r13
0x180052e24  jz      short loc_180052E4A
0x180052e26  test    [rcx+1Ch], r12b
0x180052e2a  jz      short loc_180052E4A
0x180052e2c  cmp     byte ptr [rcx+19h], 2
0x180052e30  jb      short loc_180052E4A
0x180052e32  mov     rcx, [rcx+10h]
0x180052e36  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052e3d  mov     edx, 56h ; 'V'
0x180052e42  mov     r9d, ebx
0x180052e45  call    WPP_SF_d
0x180052e4a  call    cs:__imp_GetProcessHeap
0x180052e50  mov     r8d, 16h; dwBytes
0x180052e56  mov     edx, r12d; dwFlags
0x180052e59  mov     rcx, rax; hHeap
0x180052e5c  call    cs:__imp_HeapAlloc
0x180052e62  mov     [r14], rax
0x180052e65  test    rax, rax
0x180052e68  jnz     short loc_180052ED5
0x180052e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e71  cmp     rcx, r13
0x180052e74  jz      short loc_180052ECE
0x180052e76  test    [rcx+1Ch], r12b
0x180052e7a  jz      short loc_180052EA2
0x180052e7c  cmp     byte ptr [rcx+19h], 2
0x180052e80  jb      short loc_180052EA2
0x180052e82  mov     rcx, [rcx+10h]
0x180052e86  lea     edx, [rax+57h]
0x180052e89  mov     r9d, 0C0000017h
0x180052e8f  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052e96  call    WPP_SF_d
0x180052e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ea2  cmp     rcx, r13
0x180052ea5  jz      short loc_180052ECE
0x180052ea7  test    [rcx+1Ch], r12b
0x180052eab  jz      short loc_180052ECE
0x180052ead  cmp     byte ptr [rcx+19h], 6
0x180052eb1  jb      short loc_180052ECE
0x180052eb3  mov     edx, 58h ; 'X'
0x180052eb8  mov     rcx, [rcx+10h]
0x180052ebc  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052ec3  mov     r9d, 0C0000017h
0x180052ec9  call    WPP_SF_d
0x180052ece  mov     eax, 0C0000017h
0x180052ed3  jmp     short loc_180052F1B
0x180052ed5  lea     r8, aMshomeNet; "mshome.net"
0x180052edc  mov     edx, 0Bh; unsigned __int64
0x180052ee1  mov     rcx, rax; unsigned __int16 *
0x180052ee4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ef0  cmp     rcx, r13
0x180052ef3  jz      short loc_180052F19
0x180052ef5  test    [rcx+1Ch], r12b
0x180052ef9  jz      short loc_180052F19
0x180052efb  cmp     byte ptr [rcx+19h], 6
0x180052eff  jb      short loc_180052F19
0x180052f01  mov     rcx, [rcx+10h]
0x180052f05  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180052f0c  mov     edx, 5Eh ; '^'
0x180052f11  xor     r9d, r9d
0x180052f14  call    WPP_SF_d
0x180052f19  xor     eax, eax
0x180052f1b  mov     rbx, [rsp+60h+arg_10]
0x180052f23  add     rsp, 60h
0x180052f27  pop     r15
0x180052f29  pop     r14
0x180052f2b  pop     r13
0x180052f2d  pop     r12
0x180052f2f  pop     rdi
0x180052f30  pop     rsi
0x180052f31  pop     rbp
0x180052f32  retn
```
