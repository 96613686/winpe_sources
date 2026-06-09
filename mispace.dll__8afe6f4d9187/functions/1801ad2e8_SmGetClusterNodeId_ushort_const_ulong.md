# SmGetClusterNodeId(ushort const *,ulong *)

- ea: `0x1801ad2e8`
- end: `0x1801ad3e7`
- name: `?SmGetClusterNodeId@@YAJPEBGPEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(LPCWSTR lpszNodeName, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800526d4`
- `0x1800964f8`
- `0x1800e26c0`
- `0x1800e2c10`
- `0x1800e8a24`
- `0x180114cd8`
- `0x18011f1dc`

## callees

- `0x18000cbcc`
- `0x18000cd18`
- `0x1801ad2e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801ad3a8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801ad3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad31e`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x1801ad33f`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x1801ad33f`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1801ad3c3`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1801ad3c3`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x1801ad30e`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x1801ad30e`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1801ad3d1`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1801ad3d1`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801ad357`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801ad393`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801ad357`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801ad393`

## pseudocode

```c
__int64 __fastcall SmGetClusterNodeId(LPCWSTR lpszNodeName, unsigned int *a2)
{
  struct _HCLUSTER *v4; // rax
  struct _HCLUSTER *v5; // rsi
  struct _HNODE *v6; // rdi
  signed int LastError; // eax
  signed int v8; // ebx
  struct _HNODE *v9; // rax
  DWORD cchName; // [rsp+50h] [rbp+18h] BYREF
  LPWSTR lpszNodeId; // [rsp+58h] [rbp+20h] BYREF

  lpszNodeId = 0;
  cchName = 0;
  v4 = OpenCluster(0);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 0;
LABEL_3:
    LastError = GetLastError();
    v8 = LastError;
    goto LABEL_4;
  }
  v9 = OpenClusterNode(v4, lpszNodeName);
  v6 = v9;
  if ( !v9 )
    goto LABEL_3;
  LastError = GetClusterNodeId(v9, 0, &cchName);
  v8 = LastError;
  if ( LastError && LastError != 234 )
  {
LABEL_4:
    if ( LastError <= 0 )
      goto LABEL_14;
    goto LABEL_5;
  }
  v8 = SmAllocString(++cchName, &lpszNodeId);
  if ( v8 >= 0 )
  {
    LastError = GetClusterNodeId(v6, lpszNodeId, &cchName);
    if ( LastError )
    {
      if ( LastError > 0 )
      {
LABEL_5:
        v8 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_14;
      }
      v8 = LastError;
    }
    else
    {
      *a2 = _o__wtoi(lpszNodeId);
    }
  }
LABEL_14:
  SmFreeString(&lpszNodeId);
  if ( v6 )
    CloseClusterNode(v6);
  if ( v5 )
    CloseCluster(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801ad2e8  mov     [rsp+arg_0], rbx
0x1801ad2ed  push    rsi
0x1801ad2ee  push    rdi
0x1801ad2ef  push    r14
0x1801ad2f1  sub     rsp, 20h
0x1801ad2f5  mov     rbx, rcx
0x1801ad2f8  mov     [rsp+38h+lpszNodeId], 0
0x1801ad301  xor     ecx, ecx; lpszClusterName
0x1801ad303  mov     [rsp+38h+cchName], 0
0x1801ad30b  mov     r14, rdx
0x1801ad30e  call    cs:__imp_OpenCluster
0x1801ad314  mov     rsi, rax
0x1801ad317  test    rax, rax
0x1801ad31a  jnz     short loc_1801AD339
0x1801ad31c  xor     edi, edi
0x1801ad31e  call    cs:__imp_GetLastError
0x1801ad324  mov     ebx, eax
0x1801ad326  test    eax, eax
0x1801ad328  jle     loc_1801AD3B1
0x1801ad32e  movzx   ebx, ax
0x1801ad331  or      ebx, 80070000h
0x1801ad337  jmp     short loc_1801AD3B1
0x1801ad339  mov     rdx, rbx; lpszNodeName
0x1801ad33c  mov     rcx, rsi; hCluster
0x1801ad33f  call    cs:__imp_OpenClusterNode
0x1801ad345  mov     rdi, rax
0x1801ad348  test    rax, rax
0x1801ad34b  jz      short loc_1801AD31E
0x1801ad34d  lea     r8, [rsp+38h+cchName]; lpcchName
0x1801ad352  xor     edx, edx; lpszNodeId
0x1801ad354  mov     rcx, rax; hNode
0x1801ad357  call    cs:__imp_GetClusterNodeId
0x1801ad35d  mov     ebx, eax
0x1801ad35f  test    eax, eax
0x1801ad361  jz      short loc_1801AD36A
0x1801ad363  cmp     eax, 0EAh
0x1801ad368  jnz     short loc_1801AD326
0x1801ad36a  mov     eax, [rsp+38h+cchName]
0x1801ad36e  lea     rdx, [rsp+38h+lpszNodeId]; unsigned __int16 **
0x1801ad373  inc     eax
0x1801ad375  mov     ecx, eax; unsigned __int64
0x1801ad377  mov     [rsp+38h+cchName], eax
0x1801ad37b  call    ?SmAllocString@@YAJ_KPEAPEAG@Z; SmAllocString(unsigned __int64,ushort * *)
0x1801ad380  mov     ebx, eax
0x1801ad382  test    eax, eax
0x1801ad384  js      short loc_1801AD3B1
0x1801ad386  mov     rdx, [rsp+38h+lpszNodeId]; lpszNodeId
0x1801ad38b  lea     r8, [rsp+38h+cchName]; lpcchName
0x1801ad390  mov     rcx, rdi; hNode
0x1801ad393  call    cs:__imp_GetClusterNodeId
0x1801ad399  test    eax, eax
0x1801ad39b  jz      short loc_1801AD3A3
0x1801ad39d  jg      short loc_1801AD32E
0x1801ad39f  mov     ebx, eax
0x1801ad3a1  jmp     short loc_1801AD3B1
0x1801ad3a3  mov     rcx, [rsp+38h+lpszNodeId]
0x1801ad3a8  call    cs:__imp__o__wtoi
0x1801ad3ae  mov     [r14], eax
0x1801ad3b1  lea     rcx, [rsp+38h+lpszNodeId]; unsigned __int16 **
0x1801ad3b6  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x1801ad3bb  test    rdi, rdi
0x1801ad3be  jz      short loc_1801AD3C9
0x1801ad3c0  mov     rcx, rdi; hNode
0x1801ad3c3  call    cs:__imp_CloseClusterNode
0x1801ad3c9  test    rsi, rsi
0x1801ad3cc  jz      short loc_1801AD3D7
0x1801ad3ce  mov     rcx, rsi; hCluster
0x1801ad3d1  call    cs:__imp_CloseCluster
0x1801ad3d7  mov     eax, ebx
0x1801ad3d9  mov     rbx, [rsp+38h+arg_0]
0x1801ad3de  add     rsp, 20h
0x1801ad3e2  pop     r14
0x1801ad3e4  pop     rdi
0x1801ad3e5  pop     rsi
0x1801ad3e6  retn
```
