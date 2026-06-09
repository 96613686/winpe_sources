# DfsGetDfsResourceInCluster(_HCLUSTER *,ushort const *,ushort const *,_HRESOURCE * *)

- ea: `0x140013864`
- end: `0x140013a06`
- name: `?DfsGetDfsResourceInCluster@@YAKPEAU_HCLUSTER@@PEBG1PEAPEAU_HRESOURCE@@@Z`
- size: `418`
- prototype: `unsigned int __fastcall(struct _HCLUSTER *, const unsigned __int16 *, const unsigned __int16 *, struct _HRESOURCE **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140014434`
- `0x1400144f4`

## callees

- `0x140013864`
- `0x140013a0c`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001397d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400139a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001397d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400139a2`
- `CLUSAPI!ClusterOpenEnum` at `0x1400138c4`
- `CLUSAPI!ClusterOpenEnum` at `0x1400138c4`
- `CLUSAPI!ClusterEnum` at `0x140013918`
- `CLUSAPI!ClusterEnum` at `0x140013918`
- `CLUSAPI!OpenClusterGroup` at `0x140013932`
- `CLUSAPI!OpenClusterGroup` at `0x140013932`
- `CLUSAPI!CloseClusterGroup` at `0x14001396a`
- `CLUSAPI!CloseClusterGroup` at `0x1400139b8`
- `CLUSAPI!CloseClusterGroup` at `0x14001396a`
- `CLUSAPI!CloseClusterGroup` at `0x1400139b8`
- `CLUSAPI!ClusterCloseEnum` at `0x1400139cc`
- `CLUSAPI!ClusterCloseEnum` at `0x1400139cc`

## pseudocode

```c
__int64 __fastcall DfsGetDfsResourceInCluster(
        struct _HCLUSTER *a1,
        wchar_t *a2,
        unsigned __int16 *a3,
        struct _HRESOURCE **a4)
{
  struct _HGROUP *v4; // rsi
  struct _HCLUSENUM *v8; // rdi
  DWORD i; // ebp
  unsigned int LastError; // ebx
  struct _HGROUP *v11; // rax
  DWORD cchName; // [rsp+30h] [rbp-278h] BYREF
  DWORD dwType; // [rsp+34h] [rbp-274h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-270h]
  WCHAR szName[264]; // [rsp+40h] [rbp-268h] BYREF

  v4 = 0;
  v15 = a3;
  if ( a1 && a4 && a3 && a2 )
  {
    v8 = ClusterOpenEnum(a1, 8u);
    if ( v8 )
    {
      dwType = 0;
      memset_0(szName, 0, 0x208u);
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        LastError = ClusterEnum(v8, i, &dwType, szName, &cchName);
        if ( LastError )
          break;
        v11 = OpenClusterGroup(a1, szName);
        v4 = v11;
        if ( !v11 )
        {
          LastError = GetLastError();
          goto LABEL_19;
        }
        LastError = DfsGetDfsResourceInGroup(a1, v11, a2, v15, a4);
        if ( LastError != 1168 )
          goto LABEL_13;
        CloseClusterGroup(v4);
      }
      v4 = 0;
LABEL_13:
      if ( LastError == 259 )
      {
        *a4 = 0;
        LastError = 1168;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    if ( v4 )
      CloseClusterGroup(v4);
    if ( v8 )
LABEL_19:
      ClusterCloseEnum(v8);
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x140013864  push    rbx
0x140013866  push    rbp
0x140013867  push    rsi
0x140013868  push    rdi
0x140013869  push    r12
0x14001386b  push    r13
0x14001386d  push    r14
0x14001386f  push    r15
0x140013871  sub     rsp, 268h
0x140013878  mov     rax, cs:__security_cookie
0x14001387f  xor     rax, rsp
0x140013882  mov     [rsp+2A8h+var_58], rax
0x14001388a  xor     esi, esi
0x14001388c  mov     rax, r8
0x14001388f  mov     [rsp+2A8h+var_270], rax
0x140013894  mov     r14, r9
0x140013897  mov     r13, rdx
0x14001389a  mov     r15, rcx
0x14001389d  test    rcx, rcx
0x1400138a0  jz      loc_1400139DA
0x1400138a6  test    r9, r9
0x1400138a9  jz      loc_1400139DA
0x1400138af  test    rax, rax
0x1400138b2  jz      loc_1400139DA
0x1400138b8  test    rdx, rdx
0x1400138bb  jz      loc_1400139DA
0x1400138c1  lea     edx, [rsi+8]; dwType
0x1400138c4  call    cs:__imp_ClusterOpenEnum
0x1400138cb  nop     dword ptr [rax+rax+00h]
0x1400138d0  mov     rdi, rax
0x1400138d3  mov     r12, rax
0x1400138d6  test    rax, rax
0x1400138d9  jz      loc_1400139A2
0x1400138df  and     [rsp+2A8h+dwType], esi
0x1400138e3  lea     rcx, [rsp+2A8h+szName]; void *
0x1400138e8  xor     edx, edx; Val
0x1400138ea  mov     r8d, 208h; Size
0x1400138f0  call    memset_0
0x1400138f5  xor     ebp, ebp
0x1400138f7  lea     rax, [rsp+2A8h+cchName]
0x1400138fc  mov     [rsp+2A8h+cchName], 104h
0x140013904  lea     r9, [rsp+2A8h+szName]; lpszName
0x140013909  mov     [rsp+2A8h+lpcchName], rax; lpcchName
0x14001390e  lea     r8, [rsp+2A8h+dwType]; lpdwType
0x140013913  mov     edx, ebp; dwIndex
0x140013915  mov     rcx, rdi; hEnum
0x140013918  call    cs:__imp_ClusterEnum
0x14001391f  nop     dword ptr [rax+rax+00h]
0x140013924  mov     ebx, eax
0x140013926  test    eax, eax
0x140013928  jnz     short loc_14001398D
0x14001392a  lea     rdx, [rsp+2A8h+szName]; lpszGroupName
0x14001392f  mov     rcx, r15; hCluster
0x140013932  call    cs:__imp_OpenClusterGroup
0x140013939  nop     dword ptr [rax+rax+00h]
0x14001393e  mov     rsi, rax
0x140013941  test    rax, rax
0x140013944  jz      short loc_14001397D
0x140013946  mov     r9, [rsp+2A8h+var_270]; unsigned __int16 *
0x14001394b  mov     r8, r13; unsigned __int16 *
0x14001394e  mov     rdx, rax; struct _HGROUP *
0x140013951  mov     [rsp+2A8h+lpcchName], r14; struct _HRESOURCE **
0x140013956  mov     rcx, r15; struct _HCLUSTER *
0x140013959  call    ?DfsGetDfsResourceInGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEBG2PEAPEAU_HRESOURCE@@@Z; DfsGetDfsResourceInGroup(_HCLUSTER *,_HGROUP *,ushort const *,ushort const *,_HRESOURCE * *)
0x14001395e  mov     ebx, eax
0x140013960  cmp     eax, 490h
0x140013965  jnz     short loc_14001398F
0x140013967  mov     rcx, rsi; hGroup
0x14001396a  call    cs:__imp_CloseClusterGroup
0x140013971  nop     dword ptr [rax+rax+00h]
0x140013976  inc     ebp
0x140013978  jmp     loc_1400138F7
0x14001397d  call    cs:__imp_GetLastError
0x140013984  nop     dword ptr [rax+rax+00h]
0x140013989  mov     ebx, eax
0x14001398b  jmp     short loc_1400139C9
0x14001398d  xor     esi, esi
0x14001398f  cmp     ebx, 103h
0x140013995  jnz     short loc_1400139B0
0x140013997  and     qword ptr [r14], 0
0x14001399b  mov     ebx, 490h
0x1400139a0  jmp     short loc_1400139B0
0x1400139a2  call    cs:__imp_GetLastError
0x1400139a9  nop     dword ptr [rax+rax+00h]
0x1400139ae  mov     ebx, eax
0x1400139b0  test    rsi, rsi
0x1400139b3  jz      short loc_1400139C4
0x1400139b5  mov     rcx, rsi; hGroup
0x1400139b8  call    cs:__imp_CloseClusterGroup
0x1400139bf  nop     dword ptr [rax+rax+00h]
0x1400139c4  test    rdi, rdi
0x1400139c7  jz      short loc_1400139DF
0x1400139c9  mov     rcx, rdi; hEnum
0x1400139cc  call    cs:__imp_ClusterCloseEnum
0x1400139d3  nop     dword ptr [rax+rax+00h]
0x1400139d8  jmp     short loc_1400139DF
0x1400139da  mov     ebx, 57h ; 'W'
0x1400139df  mov     eax, ebx
0x1400139e1  mov     rcx, [rsp+2A8h+var_58]
0x1400139e9  xor     rcx, rsp; StackCookie
0x1400139ec  call    __security_check_cookie
0x1400139f1  add     rsp, 268h
0x1400139f8  pop     r15
0x1400139fa  pop     r14
0x1400139fc  pop     r13
0x1400139fe  pop     r12
0x140013a00  pop     rdi
0x140013a01  pop     rsi
0x140013a02  pop     rbp
0x140013a03  pop     rbx
0x140013a04  retn
```
