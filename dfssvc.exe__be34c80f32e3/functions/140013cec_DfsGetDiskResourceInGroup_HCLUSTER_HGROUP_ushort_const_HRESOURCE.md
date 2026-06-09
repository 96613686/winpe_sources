# DfsGetDiskResourceInGroup(_HCLUSTER *,_HGROUP *,ushort const *,_HRESOURCE * *)

- ea: `0x140013cec`
- end: `0x140013eee`
- name: `?DfsGetDiskResourceInGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEBGPEAPEAU_HRESOURCE@@@Z`
- size: `514`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, HGROUP hGroup, const unsigned __int16 *lpInBuffer, struct _HRESOURCE **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014364`

## callees

- `0x140013cec`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013e85`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x140013ebb`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x140013ebb`
- `CLUSAPI!OpenClusterResource` at `0x140013dc6`
- `CLUSAPI!OpenClusterResource` at `0x140013dc6`
- `CLUSAPI!ClusterGroupEnum` at `0x140013da8`
- `CLUSAPI!ClusterGroupEnum` at `0x140013da8`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x140013d5f`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x140013d5f`
- `CLUSAPI!CloseClusterResource` at `0x140013e72`
- `CLUSAPI!CloseClusterResource` at `0x140013e72`
- `CLUSAPI!ClusterResourceControl` at `0x140013e0d`
- `CLUSAPI!ClusterResourceControl` at `0x140013e5a`
- `CLUSAPI!ClusterResourceControl` at `0x140013e0d`
- `CLUSAPI!ClusterResourceControl` at `0x140013e5a`

## pseudocode

```c
__int64 __fastcall DfsGetDiskResourceInGroup(
        HCLUSTER hCluster,
        HGROUP hGroup,
        unsigned __int16 *lpInBuffer,
        struct _HRESOURCE **a4)
{
  DWORD LastError; // ebx
  struct _HGROUPENUM *v8; // rsi
  struct _HRESOURCE *v9; // rdi
  DWORD v10; // ebp
  __int64 v11; // rax
  DWORD v12; // eax
  DWORD cchName; // [rsp+40h] [rbp-288h] BYREF
  DWORD dwType; // [rsp+44h] [rbp-284h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-280h] BYREF
  __int64 OutBuffer; // [rsp+50h] [rbp-278h] BYREF
  WCHAR szResourceName[264]; // [rsp+60h] [rbp-268h] BYREF

  OutBuffer = 0;
  BytesReturned = 0;
  LastError = 0;
  v8 = 0;
  v9 = 0;
  if ( !hCluster || !hGroup || !lpInBuffer || !a4 )
  {
    LastError = 87;
    goto LABEL_23;
  }
  v8 = ClusterGroupOpenEnum(hGroup, 1u);
  if ( v8 )
  {
    v10 = 0;
    while ( !LastError )
    {
      dwType = 0;
      cchName = 260;
      LastError = ClusterGroupEnum(v8, v10, &dwType, szResourceName, &cchName);
      if ( !LastError )
      {
        v9 = OpenClusterResource(hCluster, szResourceName);
        if ( !v9 )
          goto LABEL_18;
        if ( !ClusterResourceControl(v9, 0, 0x100000Du, 0, 0, &OutBuffer, 8u, &BytesReturned) && (_DWORD)OutBuffer == 1 )
        {
          v11 = -1;
          do
            ++v11;
          while ( lpInBuffer[v11] );
          v12 = ClusterResourceControl(v9, 0, 0x1000199u, lpInBuffer, 2 * v11 + 2, 0, 0, 0);
          if ( !v12 || v12 == 3 )
            goto LABEL_24;
        }
        CloseClusterResource(v9);
      }
      ++v10;
    }
    if ( LastError == 259 )
      LastError = 1168;
    goto LABEL_23;
  }
LABEL_18:
  LastError = GetLastError();
  if ( LastError )
LABEL_23:
    v9 = 0;
LABEL_24:
  *a4 = v9;
  if ( v8 )
    ClusterGroupCloseEnum(v8);
  return LastError;
}

```

## disassembly

```asm
0x140013cec  push    rbx
0x140013cee  push    rbp
0x140013cef  push    rsi
0x140013cf0  push    rdi
0x140013cf1  push    r12
0x140013cf3  push    r13
0x140013cf5  push    r14
0x140013cf7  push    r15
0x140013cf9  sub     rsp, 288h
0x140013d00  mov     rax, cs:__security_cookie
0x140013d07  xor     rax, rsp
0x140013d0a  mov     [rsp+2C8h+var_58], rax
0x140013d12  xor     r13d, r13d
0x140013d15  mov     r15, r9
0x140013d18  mov     [rsp+2C8h+OutBuffer], r13
0x140013d1d  mov     r14, r8
0x140013d20  mov     [rsp+2C8h+BytesReturned], r13d
0x140013d25  mov     rax, rdx
0x140013d28  mov     r12, rcx
0x140013d2b  mov     ebx, r13d
0x140013d2e  mov     esi, r13d
0x140013d31  mov     edi, r13d
0x140013d34  test    rcx, rcx
0x140013d37  jz      loc_140013EA8
0x140013d3d  test    rax, rax
0x140013d40  jz      loc_140013EA8
0x140013d46  test    r8, r8
0x140013d49  jz      loc_140013EA8
0x140013d4f  test    r9, r9
0x140013d52  jz      loc_140013EA8
0x140013d58  lea     edx, [r13+1]; dwType
0x140013d5c  mov     rcx, rax; hGroup
0x140013d5f  call    cs:__imp_ClusterGroupOpenEnum
0x140013d66  nop     dword ptr [rax+rax+00h]
0x140013d6b  mov     rsi, rax
0x140013d6e  test    rax, rax
0x140013d71  jz      loc_140013E85
0x140013d77  mov     ebp, r13d
0x140013d7a  test    ebx, ebx
0x140013d7c  jnz     loc_140013E99
0x140013d82  lea     rax, [rsp+2C8h+cchName]
0x140013d87  mov     [rsp+2C8h+dwType], r13d
0x140013d8c  lea     r9, [rsp+2C8h+szResourceName]; lpszResourceName
0x140013d91  mov     [rsp+2C8h+lpcchName], rax; lpcchName
0x140013d96  lea     r8, [rsp+2C8h+dwType]; lpdwType
0x140013d9b  mov     [rsp+2C8h+cchName], 104h
0x140013da3  mov     edx, ebp; dwIndex
0x140013da5  mov     rcx, rsi; hGroupEnum
0x140013da8  call    cs:__imp_ClusterGroupEnum
0x140013daf  nop     dword ptr [rax+rax+00h]
0x140013db4  mov     ebx, eax
0x140013db6  test    eax, eax
0x140013db8  jnz     loc_140013E7E
0x140013dbe  lea     rdx, [rsp+2C8h+szResourceName]; lpszResourceName
0x140013dc3  mov     rcx, r12; hCluster
0x140013dc6  call    cs:__imp_OpenClusterResource
0x140013dcd  nop     dword ptr [rax+rax+00h]
0x140013dd2  mov     rdi, rax
0x140013dd5  test    rax, rax
0x140013dd8  jz      loc_140013E85
0x140013dde  lea     rax, [rsp+2C8h+BytesReturned]
0x140013de3  xor     r9d, r9d; lpInBuffer
0x140013de6  mov     [rsp+2C8h+lpBytesReturned], rax; lpBytesReturned
0x140013deb  xor     edx, edx; hHostNode
0x140013ded  lea     rax, [rsp+2C8h+OutBuffer]
0x140013df2  mov     [rsp+2C8h+cbOutBufferSize], 8; cbOutBufferSize
0x140013dfa  mov     [rsp+2C8h+lpOutBuffer], rax; lpOutBuffer
0x140013dff  mov     r8d, 100000Dh; dwControlCode
0x140013e05  mov     rcx, rdi; hResource
0x140013e08  mov     dword ptr [rsp+2C8h+lpcchName], r13d; cbInBufferSize
0x140013e0d  call    cs:__imp_ClusterResourceControl
0x140013e14  nop     dword ptr [rax+rax+00h]
0x140013e19  test    eax, eax
0x140013e1b  jnz     short loc_140013E6F
0x140013e1d  cmp     dword ptr [rsp+2C8h+OutBuffer], 1
0x140013e22  jnz     short loc_140013E6F
0x140013e24  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013e28  inc     rax
0x140013e2b  cmp     [r14+rax*2], r13w
0x140013e30  jnz     short loc_140013E28
0x140013e32  mov     [rsp+2C8h+lpBytesReturned], r13; lpBytesReturned
0x140013e37  lea     eax, ds:2[rax*2]
0x140013e3e  mov     [rsp+2C8h+cbOutBufferSize], r13d; cbOutBufferSize
0x140013e43  mov     r9, r14; lpInBuffer
0x140013e46  mov     [rsp+2C8h+lpOutBuffer], r13; lpOutBuffer
0x140013e4b  xor     edx, edx; hHostNode
0x140013e4d  mov     r8d, 1000199h; dwControlCode
0x140013e53  mov     dword ptr [rsp+2C8h+lpcchName], eax; cbInBufferSize
0x140013e57  mov     rcx, rdi; hResource
0x140013e5a  call    cs:__imp_ClusterResourceControl
0x140013e61  nop     dword ptr [rax+rax+00h]
0x140013e66  test    eax, eax
0x140013e68  jz      short loc_140013EB0
0x140013e6a  cmp     eax, 3
0x140013e6d  jz      short loc_140013EB0
0x140013e6f  mov     rcx, rdi; hResource
0x140013e72  call    cs:__imp_CloseClusterResource
0x140013e79  nop     dword ptr [rax+rax+00h]
0x140013e7e  inc     ebp
0x140013e80  jmp     loc_140013D7A
0x140013e85  call    cs:__imp_GetLastError
0x140013e8c  nop     dword ptr [rax+rax+00h]
0x140013e91  mov     ebx, eax
0x140013e93  test    eax, eax
0x140013e95  jnz     short loc_140013EAD
0x140013e97  jmp     short loc_140013EB0
0x140013e99  cmp     ebx, 103h
0x140013e9f  jnz     short loc_140013EAD
0x140013ea1  mov     ebx, 490h
0x140013ea6  jmp     short loc_140013EAD
0x140013ea8  mov     ebx, 57h ; 'W'
0x140013ead  mov     rdi, r13
0x140013eb0  mov     [r15], rdi
0x140013eb3  test    rsi, rsi
0x140013eb6  jz      short loc_140013EC7
0x140013eb8  mov     rcx, rsi; hGroupEnum
0x140013ebb  call    cs:__imp_ClusterGroupCloseEnum
0x140013ec2  nop     dword ptr [rax+rax+00h]
0x140013ec7  mov     eax, ebx
0x140013ec9  mov     rcx, [rsp+2C8h+var_58]
0x140013ed1  xor     rcx, rsp; StackCookie
0x140013ed4  call    __security_check_cookie
0x140013ed9  add     rsp, 288h
0x140013ee0  pop     r15
0x140013ee2  pop     r14
0x140013ee4  pop     r13
0x140013ee6  pop     r12
0x140013ee8  pop     rdi
0x140013ee9  pop     rsi
0x140013eea  pop     rbp
0x140013eeb  pop     rbx
0x140013eec  retn
```
