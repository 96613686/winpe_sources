# DfsGetNetworkNameResourceInCluster(_HCLUSTER *,ushort const *,_HRESOURCE * *,_HGROUP * *)

- ea: `0x140013ef4`
- end: `0x140014075`
- name: `?DfsGetNetworkNameResourceInCluster@@YAKPEAU_HCLUSTER@@PEBGPEAPEAU_HRESOURCE@@PEAPEAU_HGROUP@@@Z`
- size: `385`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, const unsigned __int16 *, struct _HRESOURCE **, struct _HGROUP **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014364`

## callees

- `0x140013ef4`
- `0x14001407c`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014007`
- `CLUSAPI!ClusterOpenEnum` at `0x140013f46`
- `CLUSAPI!ClusterOpenEnum` at `0x140013f46`
- `CLUSAPI!ClusterEnum` at `0x140013f97`
- `CLUSAPI!ClusterEnum` at `0x140013f97`
- `CLUSAPI!OpenClusterGroup` at `0x140013fb1`
- `CLUSAPI!OpenClusterGroup` at `0x140013fb1`
- `CLUSAPI!CloseClusterGroup` at `0x140013fe2`
- `CLUSAPI!CloseClusterGroup` at `0x140014027`
- `CLUSAPI!CloseClusterGroup` at `0x140013fe2`
- `CLUSAPI!CloseClusterGroup` at `0x140014027`
- `CLUSAPI!ClusterCloseEnum` at `0x14001403b`
- `CLUSAPI!ClusterCloseEnum` at `0x14001403b`

## pseudocode

```c
__int64 __fastcall DfsGetNetworkNameResourceInCluster(
        HCLUSTER hCluster,
        unsigned __int16 *a2,
        struct _HRESOURCE **a3,
        struct _HGROUP **a4)
{
  struct _HGROUP *v4; // rdi
  struct _HCLUSENUM *v9; // rsi
  DWORD i; // ebp
  unsigned int NetworkNameResourceInGroup; // ebx
  struct _HGROUP *v12; // rax
  DWORD cchName; // [rsp+30h] [rbp-278h] BYREF
  DWORD dwType[3]; // [rsp+34h] [rbp-274h] BYREF
  WCHAR szName[264]; // [rsp+40h] [rbp-268h] BYREF

  v4 = 0;
  if ( hCluster && a3 && a2 )
  {
    v9 = ClusterOpenEnum(hCluster, 8u);
    if ( v9 )
    {
      dwType[0] = 0;
      memset_0(szName, 0, 0x208u);
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        NetworkNameResourceInGroup = ClusterEnum(v9, i, dwType, szName, &cchName);
        if ( NetworkNameResourceInGroup )
          break;
        v12 = OpenClusterGroup(hCluster, szName);
        v4 = v12;
        if ( !v12 )
          goto LABEL_13;
        NetworkNameResourceInGroup = DfsGetNetworkNameResourceInGroup(hCluster, v12, a2, a3);
        if ( NetworkNameResourceInGroup != 1168 )
          goto LABEL_11;
        CloseClusterGroup(v4);
      }
      v4 = 0;
LABEL_11:
      if ( NetworkNameResourceInGroup == 259 )
      {
        *a3 = 0;
        NetworkNameResourceInGroup = 5047;
      }
    }
    else
    {
LABEL_13:
      NetworkNameResourceInGroup = GetLastError();
    }
    if ( NetworkNameResourceInGroup )
    {
      if ( v4 )
        CloseClusterGroup(v4);
    }
    else
    {
      *a4 = v4;
    }
    if ( v9 )
      ClusterCloseEnum(v9);
  }
  else
  {
    return 87;
  }
  return NetworkNameResourceInGroup;
}

```

## disassembly

```asm
0x140013ef4  push    rbx
0x140013ef6  push    rbp
0x140013ef7  push    rsi
0x140013ef8  push    rdi
0x140013ef9  push    r12
0x140013efb  push    r13
0x140013efd  push    r14
0x140013eff  push    r15
0x140013f01  sub     rsp, 268h
0x140013f08  mov     rax, cs:__security_cookie
0x140013f0f  xor     rax, rsp
0x140013f12  mov     [rsp+2A8h+var_58], rax
0x140013f1a  xor     edi, edi
0x140013f1c  mov     r13, r9
0x140013f1f  mov     r14, r8
0x140013f22  mov     r12, rdx
0x140013f25  mov     r15, rcx
0x140013f28  test    rcx, rcx
0x140013f2b  jz      loc_140014049
0x140013f31  test    r8, r8
0x140013f34  jz      loc_140014049
0x140013f3a  test    rdx, rdx
0x140013f3d  jz      loc_140014049
0x140013f43  lea     edx, [rdi+8]; dwType
0x140013f46  call    cs:__imp_ClusterOpenEnum
0x140013f4d  nop     dword ptr [rax+rax+00h]
0x140013f52  mov     rsi, rax
0x140013f55  test    rax, rax
0x140013f58  jz      loc_140014007
0x140013f5e  and     [rsp+2A8h+dwType], edi
0x140013f62  lea     rcx, [rsp+2A8h+szName]; void *
0x140013f67  xor     edx, edx; Val
0x140013f69  mov     r8d, 208h; Size
0x140013f6f  call    memset_0
0x140013f74  xor     ebp, ebp
0x140013f76  lea     rax, [rsp+2A8h+cchName]
0x140013f7b  mov     [rsp+2A8h+cchName], 104h
0x140013f83  lea     r9, [rsp+2A8h+szName]; lpszName
0x140013f88  mov     [rsp+2A8h+lpcchName], rax; lpcchName
0x140013f8d  lea     r8, [rsp+2A8h+dwType]; lpdwType
0x140013f92  mov     edx, ebp; dwIndex
0x140013f94  mov     rcx, rsi; hEnum
0x140013f97  call    cs:__imp_ClusterEnum
0x140013f9e  nop     dword ptr [rax+rax+00h]
0x140013fa3  mov     ebx, eax
0x140013fa5  test    eax, eax
0x140013fa7  jnz     short loc_140013FF2
0x140013fa9  lea     rdx, [rsp+2A8h+szName]; lpszGroupName
0x140013fae  mov     rcx, r15; hCluster
0x140013fb1  call    cs:__imp_OpenClusterGroup
0x140013fb8  nop     dword ptr [rax+rax+00h]
0x140013fbd  mov     rdi, rax
0x140013fc0  test    rax, rax
0x140013fc3  jz      short loc_140014007
0x140013fc5  mov     r9, r14; struct _HRESOURCE **
0x140013fc8  mov     r8, r12; unsigned __int16 *
0x140013fcb  mov     rdx, rax; hGroup
0x140013fce  mov     rcx, r15; hCluster
0x140013fd1  call    ?DfsGetNetworkNameResourceInGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEBGPEAPEAU_HRESOURCE@@@Z; DfsGetNetworkNameResourceInGroup(_HCLUSTER *,_HGROUP *,ushort const *,_HRESOURCE * *)
0x140013fd6  mov     ebx, eax
0x140013fd8  cmp     eax, 490h
0x140013fdd  jnz     short loc_140013FF4
0x140013fdf  mov     rcx, rdi; hGroup
0x140013fe2  call    cs:__imp_CloseClusterGroup
0x140013fe9  nop     dword ptr [rax+rax+00h]
0x140013fee  inc     ebp
0x140013ff0  jmp     short loc_140013F76
0x140013ff2  xor     edi, edi
0x140013ff4  cmp     ebx, 103h
0x140013ffa  jnz     short loc_140014015
0x140013ffc  and     qword ptr [r14], 0
0x140014000  mov     ebx, 13B7h
0x140014005  jmp     short loc_140014015
0x140014007  call    cs:__imp_GetLastError
0x14001400e  nop     dword ptr [rax+rax+00h]
0x140014013  mov     ebx, eax
0x140014015  test    ebx, ebx
0x140014017  jnz     short loc_14001401F
0x140014019  mov     [r13+0], rdi
0x14001401d  jmp     short loc_140014033
0x14001401f  test    rdi, rdi
0x140014022  jz      short loc_140014033
0x140014024  mov     rcx, rdi; hGroup
0x140014027  call    cs:__imp_CloseClusterGroup
0x14001402e  nop     dword ptr [rax+rax+00h]
0x140014033  test    rsi, rsi
0x140014036  jz      short loc_14001404E
0x140014038  mov     rcx, rsi; hEnum
0x14001403b  call    cs:__imp_ClusterCloseEnum
0x140014042  nop     dword ptr [rax+rax+00h]
0x140014047  jmp     short loc_14001404E
0x140014049  mov     ebx, 57h ; 'W'
0x14001404e  mov     eax, ebx
0x140014050  mov     rcx, [rsp+2A8h+var_58]
0x140014058  xor     rcx, rsp; StackCookie
0x14001405b  call    __security_check_cookie
0x140014060  add     rsp, 268h
0x140014067  pop     r15
0x140014069  pop     r14
0x14001406b  pop     r13
0x14001406d  pop     r12
0x14001406f  pop     rdi
0x140014070  pop     rsi
0x140014071  pop     rbp
0x140014072  pop     rbx
0x140014073  retn
```
