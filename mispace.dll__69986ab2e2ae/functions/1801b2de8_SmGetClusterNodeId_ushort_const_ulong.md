# SmGetClusterNodeId(ushort const *,ulong *)

- ea: `0x1801b2de8`
- end: `0x1801b2f1f`
- name: `?SmGetClusterNodeId@@YAJPEBGPEAK@Z`
- size: `311`
- prototype: `__int64 __fastcall(LPCWSTR lpszNodeName, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180054170`
- `0x180098de4`
- `0x1800e5d30`
- `0x1800e6250`
- `0x1800ebfb4`
- `0x1801187cc`
- `0x180122e98`

## callees

- `0x18000cb2c`
- `0x18000cc78`
- `0x1801b2de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801b2ecd`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801b2ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2e24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2e24`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x1801b2e4e`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x1801b2e4e`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1801b2eee`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1801b2eee`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x1801b2e0e`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x1801b2e0e`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1801b2f02`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1801b2f02`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801b2e6c`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801b2eae`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801b2e6c`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1801b2eae`

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
0x1801b2de8  mov     [rsp+arg_0], rbx
0x1801b2ded  push    rsi
0x1801b2dee  push    rdi
0x1801b2def  push    r14
0x1801b2df1  sub     rsp, 20h
0x1801b2df5  mov     rbx, rcx
0x1801b2df8  mov     [rsp+38h+lpszNodeId], 0
0x1801b2e01  xor     ecx, ecx; lpszClusterName
0x1801b2e03  mov     [rsp+38h+cchName], 0
0x1801b2e0b  mov     r14, rdx
0x1801b2e0e  call    cs:__imp_OpenCluster
0x1801b2e15  nop     dword ptr [rax+rax+00h]
0x1801b2e1a  mov     rsi, rax
0x1801b2e1d  test    rax, rax
0x1801b2e20  jnz     short loc_1801B2E48
0x1801b2e22  xor     edi, edi
0x1801b2e24  call    cs:__imp_GetLastError
0x1801b2e2b  nop     dword ptr [rax+rax+00h]
0x1801b2e30  mov     ebx, eax
0x1801b2e32  test    eax, eax
0x1801b2e34  jle     loc_1801B2EDC
0x1801b2e3a  movzx   ebx, ax
0x1801b2e3d  or      ebx, 80070000h
0x1801b2e43  jmp     loc_1801B2EDC
0x1801b2e48  mov     rdx, rbx; lpszNodeName
0x1801b2e4b  mov     rcx, rsi; hCluster
0x1801b2e4e  call    cs:__imp_OpenClusterNode
0x1801b2e55  nop     dword ptr [rax+rax+00h]
0x1801b2e5a  mov     rdi, rax
0x1801b2e5d  test    rax, rax
0x1801b2e60  jz      short loc_1801B2E24
0x1801b2e62  lea     r8, [rsp+38h+cchName]; lpcchName
0x1801b2e67  xor     edx, edx; lpszNodeId
0x1801b2e69  mov     rcx, rax; hNode
0x1801b2e6c  call    cs:__imp_GetClusterNodeId
0x1801b2e73  nop     dword ptr [rax+rax+00h]
0x1801b2e78  mov     ebx, eax
0x1801b2e7a  test    eax, eax
0x1801b2e7c  jz      short loc_1801B2E85
0x1801b2e7e  cmp     eax, 0EAh
0x1801b2e83  jnz     short loc_1801B2E32
0x1801b2e85  mov     eax, [rsp+38h+cchName]
0x1801b2e89  lea     rdx, [rsp+38h+lpszNodeId]; unsigned __int16 **
0x1801b2e8e  inc     eax
0x1801b2e90  mov     ecx, eax; unsigned __int64
0x1801b2e92  mov     [rsp+38h+cchName], eax
0x1801b2e96  call    ?SmAllocString@@YAJ_KPEAPEAG@Z; SmAllocString(unsigned __int64,ushort * *)
0x1801b2e9b  mov     ebx, eax
0x1801b2e9d  test    eax, eax
0x1801b2e9f  js      short loc_1801B2EDC
0x1801b2ea1  mov     rdx, [rsp+38h+lpszNodeId]; lpszNodeId
0x1801b2ea6  lea     r8, [rsp+38h+cchName]; lpcchName
0x1801b2eab  mov     rcx, rdi; hNode
0x1801b2eae  call    cs:__imp_GetClusterNodeId
0x1801b2eb5  nop     dword ptr [rax+rax+00h]
0x1801b2eba  test    eax, eax
0x1801b2ebc  jz      short loc_1801B2EC8
0x1801b2ebe  jg      loc_1801B2E3A
0x1801b2ec4  mov     ebx, eax
0x1801b2ec6  jmp     short loc_1801B2EDC
0x1801b2ec8  mov     rcx, [rsp+38h+lpszNodeId]
0x1801b2ecd  call    cs:__imp__o__wtoi
0x1801b2ed4  nop     dword ptr [rax+rax+00h]
0x1801b2ed9  mov     [r14], eax
0x1801b2edc  lea     rcx, [rsp+38h+lpszNodeId]; unsigned __int16 **
0x1801b2ee1  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x1801b2ee6  test    rdi, rdi
0x1801b2ee9  jz      short loc_1801B2EFA
0x1801b2eeb  mov     rcx, rdi; hNode
0x1801b2eee  call    cs:__imp_CloseClusterNode
0x1801b2ef5  nop     dword ptr [rax+rax+00h]
0x1801b2efa  test    rsi, rsi
0x1801b2efd  jz      short loc_1801B2F0E
0x1801b2eff  mov     rcx, rsi; hCluster
0x1801b2f02  call    cs:__imp_CloseCluster
0x1801b2f09  nop     dword ptr [rax+rax+00h]
0x1801b2f0e  mov     eax, ebx
0x1801b2f10  mov     rbx, [rsp+38h+arg_0]
0x1801b2f15  add     rsp, 20h
0x1801b2f19  pop     r14
0x1801b2f1b  pop     rdi
0x1801b2f1c  pop     rsi
0x1801b2f1d  retn
```
