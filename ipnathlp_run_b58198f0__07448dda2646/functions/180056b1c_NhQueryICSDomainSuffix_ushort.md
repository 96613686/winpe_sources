# NhQueryICSDomainSuffix(ushort * *)

- ea: `0x180056b1c`
- end: `0x180056fea`
- name: `?NhQueryICSDomainSuffix@@YAJPEAPEAG@Z`
- size: `1230`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180082424`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180037994`
- `0x180038aa8`
- `0x180056b1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056ef4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056ef4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056f0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056f0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056e2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056e51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056e2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056e51`
- `ntdll!RtlInitUnicodeString` at `0x180056c0c`
- `ntdll!RtlInitUnicodeString` at `0x180056c0c`
- `ntdll!NtOpenKey` at `0x180056c47`
- `ntdll!NtOpenKey` at `0x180056c47`
- `ntdll!NtClose` at `0x180056cd1`
- `ntdll!NtClose` at `0x180056cd1`

## string_xrefs

- `0x180056bfe`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

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
0x180056b1c  mov     [rsp-38h+arg_10], rbx
0x180056b21  push    rbp
0x180056b22  push    rsi
0x180056b23  push    rdi
0x180056b24  push    r12
0x180056b26  push    r13
0x180056b28  push    r14
0x180056b2a  push    r15
0x180056b2c  mov     rbp, rsp
0x180056b2f  sub     rsp, 60h
0x180056b33  mov     r14, rcx
0x180056b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b3d  lea     r13, WPP_GLOBAL_Control
0x180056b44  mov     r12d, 8
0x180056b4a  cmp     rcx, r13
0x180056b4d  jz      short loc_180056B77
0x180056b4f  test    [rcx+1Ch], r12b
0x180056b53  jz      short loc_180056B77
0x180056b55  cmp     byte ptr [rcx+19h], 6
0x180056b59  jb      short loc_180056B77
0x180056b5b  mov     rcx, [rcx+10h]
0x180056b5f  lea     edx, [r12+49h]
0x180056b64  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056b6b  call    WPP_SF_
0x180056b70  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b77  xorps   xmm0, xmm0
0x180056b7a  xor     r15d, r15d
0x180056b7d  mov     [rbp+lpMem], r15
0x180056b81  mov     [rbp+KeyHandle], r15
0x180056b85  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180056b89  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180056b8d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180056b91  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180056b95  test    r14, r14
0x180056b98  jnz     short loc_180056BFE
0x180056b9a  mov     ebx, 0C000000Dh
0x180056b9f  cmp     rcx, r13
0x180056ba2  jz      short loc_180056BF7
0x180056ba4  test    [rcx+1Ch], r12b
0x180056ba8  jz      short loc_180056BCE
0x180056baa  cmp     byte ptr [rcx+19h], 2
0x180056bae  jb      short loc_180056BCE
0x180056bb0  mov     rcx, [rcx+10h]
0x180056bb4  lea     edx, [r15+52h]
0x180056bb8  mov     r9d, ebx
0x180056bbb  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056bc2  call    WPP_SF_d
0x180056bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bce  cmp     rcx, r13
0x180056bd1  jz      short loc_180056BF7
0x180056bd3  test    [rcx+1Ch], r12b
0x180056bd7  jz      short loc_180056BF7
0x180056bd9  cmp     byte ptr [rcx+19h], 6
0x180056bdd  jb      short loc_180056BF7
0x180056bdf  mov     edx, 53h ; 'S'
0x180056be4  mov     rcx, [rcx+10h]
0x180056be8  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056bef  mov     r9d, ebx
0x180056bf2  call    WPP_SF_d
0x180056bf7  mov     eax, ebx
0x180056bf9  jmp     loc_180056FD1
0x180056bfe  lea     rdx, ?NhTcpipParametersString@@3QBGB; "\\Registry\\Machine\\System\\CurrentCon"...
0x180056c05  mov     [r14], r15
0x180056c08  lea     rcx, [rbp+DestinationString]; DestinationString
0x180056c0c  call    cs:__imp_RtlInitUnicodeString
0x180056c13  nop     dword ptr [rax+rax+00h]
0x180056c18  lea     rax, [rbp+DestinationString]
0x180056c1c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180056c23  xorps   xmm0, xmm0
0x180056c26  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180056c2a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180056c2e  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x180056c32  mov     edx, 20019h; DesiredAccess
0x180056c37  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180056c3e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180056c42  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180056c47  call    cs:__imp_NtOpenKey
0x180056c4e  nop     dword ptr [rax+rax+00h]
0x180056c53  mov     ebx, eax
0x180056c55  test    eax, eax
0x180056c57  jns     short loc_180056CB7
0x180056c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c60  cmp     rcx, r13
0x180056c63  jz      short loc_180056BF7
0x180056c65  test    [rcx+1Ch], r12b
0x180056c69  jz      short loc_180056C90
0x180056c6b  cmp     byte ptr [rcx+19h], 2
0x180056c6f  jb      short loc_180056C90
0x180056c71  mov     rcx, [rcx+10h]
0x180056c75  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056c7c  mov     edx, 54h ; 'T'
0x180056c81  mov     r9d, eax
0x180056c84  call    WPP_SF_d
0x180056c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c90  cmp     rcx, r13
0x180056c93  jz      loc_180056BF7
0x180056c99  test    [rcx+1Ch], r12b
0x180056c9d  jz      loc_180056BF7
0x180056ca3  cmp     byte ptr [rcx+19h], 6
0x180056ca7  jb      loc_180056BF7
0x180056cad  mov     edx, 55h ; 'U'
0x180056cb2  jmp     loc_180056BE4
0x180056cb7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180056cbb  lea     r8, [rbp+lpMem]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180056cbf  lea     rdx, aIcsdomain_0; "ICSDomain"
0x180056cc6  call    ?NhQueryValueKey@@YAJPEAXQEBGPEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@@Z; NhQueryValueKey(void *,ushort const * const,_KEY_VALUE_PARTIAL_INFORMATION * *)
0x180056ccb  mov     rcx, [rbp+KeyHandle]; Handle
0x180056ccf  mov     ebx, eax
0x180056cd1  call    cs:__imp_NtClose
0x180056cd8  nop     dword ptr [rax+rax+00h]
0x180056cdd  test    ebx, ebx
0x180056cdf  js      loc_180056EC4
0x180056ce5  mov     rdi, [rbp+lpMem]
0x180056ce9  test    rdi, rdi
0x180056cec  jz      loc_180056EC4
0x180056cf2  cmp     dword ptr [rdi+4], 1
0x180056cf6  jnz     loc_180056E3D
0x180056cfc  mov     ecx, [rdi+8]
0x180056cff  cmp     r15w, [rcx+rdi+0Ah]
0x180056d05  jnz     loc_180056E3D
0x180056d0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180056d0f  inc     rax
0x180056d12  cmp     [rdi+rax*2+0Ch], r15w
0x180056d18  jnz     short loc_180056D0F
0x180056d1a  inc     eax
0x180056d1c  mov     r15d, eax
0x180056d1f  lea     rbx, [rax+rax]
0x180056d23  call    cs:__imp_GetProcessHeap
0x180056d2a  nop     dword ptr [rax+rax+00h]
0x180056d2f  mov     r8, rbx; dwBytes
0x180056d32  mov     edx, r12d; dwFlags
0x180056d35  mov     rcx, rax; hHeap
0x180056d38  call    cs:__imp_HeapAlloc
0x180056d3f  nop     dword ptr [rax+rax+00h]
0x180056d44  mov     [r14], rax
0x180056d47  test    rax, rax
0x180056d4a  jnz     loc_180056DD5
0x180056d50  call    cs:__imp_GetProcessHeap
0x180056d57  nop     dword ptr [rax+rax+00h]
0x180056d5c  mov     r8, rdi; lpMem
0x180056d5f  xor     edx, edx; dwFlags
0x180056d61  mov     rcx, rax; hHeap
0x180056d64  call    cs:__imp_HeapFree
0x180056d6b  nop     dword ptr [rax+rax+00h]
0x180056d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d77  cmp     rcx, r13
0x180056d7a  jz      loc_180056F84
0x180056d80  test    [rcx+1Ch], r12b
0x180056d84  jz      short loc_180056DAE
0x180056d86  cmp     byte ptr [rcx+19h], 2
0x180056d8a  jb      short loc_180056DAE
0x180056d8c  mov     rcx, [rcx+10h]
0x180056d90  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056d97  mov     edx, 5Bh ; '['
0x180056d9c  mov     r9d, 0C0000017h
0x180056da2  call    WPP_SF_d
0x180056da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180056dae  cmp     rcx, r13
0x180056db1  jz      loc_180056F84
0x180056db7  test    [rcx+1Ch], r12b
0x180056dbb  jz      loc_180056F84
0x180056dc1  cmp     byte ptr [rcx+19h], 6
0x180056dc5  jb      loc_180056F84
0x180056dcb  mov     edx, 5Ch ; '\'
0x180056dd0  jmp     loc_180056F6E
0x180056dd5  lea     r8, [rdi+0Ch]; unsigned __int16 *
0x180056dd9  mov     rdx, r15; unsigned __int64
0x180056ddc  mov     rcx, rax; unsigned __int16 *
0x180056ddf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056de4  test    eax, eax
0x180056de6  jns     short loc_180056E18
0x180056de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180056def  cmp     rcx, r13
0x180056df2  jz      short loc_180056E18
0x180056df4  test    [rcx+1Ch], r12b
0x180056df8  jz      short loc_180056E18
0x180056dfa  cmp     byte ptr [rcx+19h], 2
0x180056dfe  jb      short loc_180056E18
0x180056e00  mov     rcx, [rcx+10h]
0x180056e04  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056e0b  mov     edx, 5Dh ; ']'
0x180056e10  mov     r9d, eax
0x180056e13  call    WPP_SF_d
0x180056e18  call    cs:__imp_GetProcessHeap
0x180056e1f  nop     dword ptr [rax+rax+00h]
0x180056e24  mov     r8, rdi; lpMem
0x180056e27  xor     edx, edx; dwFlags
0x180056e29  mov     rcx, rax; hHeap
0x180056e2c  call    cs:__imp_HeapFree
0x180056e33  nop     dword ptr [rax+rax+00h]
0x180056e38  jmp     loc_180056F9F
0x180056e3d  call    cs:__imp_GetProcessHeap
0x180056e44  nop     dword ptr [rax+rax+00h]
0x180056e49  mov     r8, rdi; lpMem
0x180056e4c  xor     edx, edx; dwFlags
0x180056e4e  mov     rcx, rax; hHeap
0x180056e51  call    cs:__imp_HeapFree
0x180056e58  nop     dword ptr [rax+rax+00h]
0x180056e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e64  mov     ebx, 0C0000001h
0x180056e69  cmp     rcx, r13
0x180056e6c  jz      loc_180056BF7
0x180056e72  test    [rcx+1Ch], r12b
0x180056e76  jz      short loc_180056E9D
0x180056e78  cmp     byte ptr [rcx+19h], 2
0x180056e7c  jb      short loc_180056E9D
0x180056e7e  mov     rcx, [rcx+10h]
0x180056e82  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056e89  mov     edx, 59h ; 'Y'
0x180056e8e  mov     r9d, ebx
0x180056e91  call    WPP_SF_d
0x180056e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e9d  cmp     rcx, r13
0x180056ea0  jz      loc_180056BF7
0x180056ea6  test    [rcx+1Ch], r12b
0x180056eaa  jz      loc_180056BF7
0x180056eb0  cmp     byte ptr [rcx+19h], 6
0x180056eb4  jb      loc_180056BF7
0x180056eba  mov     edx, 5Ah ; 'Z'
0x180056ebf  jmp     loc_180056BE4
0x180056ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ecb  cmp     rcx, r13
0x180056ece  jz      short loc_180056EF4
0x180056ed0  test    [rcx+1Ch], r12b
0x180056ed4  jz      short loc_180056EF4
0x180056ed6  cmp     byte ptr [rcx+19h], 2
0x180056eda  jb      short loc_180056EF4
0x180056edc  mov     rcx, [rcx+10h]
0x180056ee0  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056ee7  mov     edx, 56h ; 'V'
0x180056eec  mov     r9d, ebx
0x180056eef  call    WPP_SF_d
0x180056ef4  call    cs:__imp_GetProcessHeap
0x180056efb  nop     dword ptr [rax+rax+00h]
0x180056f00  mov     r8d, 16h; dwBytes
0x180056f06  mov     edx, r12d; dwFlags
0x180056f09  mov     rcx, rax; hHeap
0x180056f0c  call    cs:__imp_HeapAlloc
0x180056f13  nop     dword ptr [rax+rax+00h]
0x180056f18  mov     [r14], rax
0x180056f1b  test    rax, rax
0x180056f1e  jnz     short loc_180056F8B
0x180056f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f27  cmp     rcx, r13
0x180056f2a  jz      short loc_180056F84
0x180056f2c  test    [rcx+1Ch], r12b
0x180056f30  jz      short loc_180056F58
0x180056f32  cmp     byte ptr [rcx+19h], 2
0x180056f36  jb      short loc_180056F58
0x180056f38  mov     rcx, [rcx+10h]
0x180056f3c  lea     edx, [rax+57h]
0x180056f3f  mov     r9d, 0C0000017h
0x180056f45  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056f4c  call    WPP_SF_d
0x180056f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f58  cmp     rcx, r13
0x180056f5b  jz      short loc_180056F84
0x180056f5d  test    [rcx+1Ch], r12b
0x180056f61  jz      short loc_180056F84
0x180056f63  cmp     byte ptr [rcx+19h], 6
0x180056f67  jb      short loc_180056F84
0x180056f69  mov     edx, 58h ; 'X'
0x180056f6e  mov     rcx, [rcx+10h]
0x180056f72  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056f79  mov     r9d, 0C0000017h
0x180056f7f  call    WPP_SF_d
0x180056f84  mov     eax, 0C0000017h
0x180056f89  jmp     short loc_180056FD1
0x180056f8b  lea     r8, aMshomeNet; "mshome.net"
0x180056f92  mov     edx, 0Bh; unsigned __int64
0x180056f97  mov     rcx, rax; unsigned __int16 *
0x180056f9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fa6  cmp     rcx, r13
0x180056fa9  jz      short loc_180056FCF
0x180056fab  test    [rcx+1Ch], r12b
0x180056faf  jz      short loc_180056FCF
0x180056fb1  cmp     byte ptr [rcx+19h], 6
0x180056fb5  jb      short loc_180056FCF
0x180056fb7  mov     rcx, [rcx+10h]
0x180056fbb  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180056fc2  mov     edx, 5Eh ; '^'
0x180056fc7  xor     r9d, r9d
0x180056fca  call    WPP_SF_d
0x180056fcf  xor     eax, eax
0x180056fd1  mov     rbx, [rsp+60h+arg_10]
0x180056fd9  add     rsp, 60h
0x180056fdd  pop     r15
0x180056fdf  pop     r14
0x180056fe1  pop     r13
0x180056fe3  pop     r12
0x180056fe5  pop     rdi
0x180056fe6  pop     rsi
0x180056fe7  pop     rbp
0x180056fe8  retn
```
