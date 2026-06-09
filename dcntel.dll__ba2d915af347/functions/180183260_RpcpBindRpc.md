# RpcpBindRpc

- ea: `0x180183260`
- end: `0x180183575`
- name: `RpcpBindRpc`
- size: `789`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1801831f0`

## callees

- `0x180008dc0`
- `0x180009e6c`
- `0x180009efc`
- `0x180183260`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801833d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801834e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180183536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180183549`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801833d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801834e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180183536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180183549`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801832fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180183382`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801833ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801832fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180183382`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801833ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180183348`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801833ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180183348`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801833ad`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801834da`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801834da`
- `RPCRT4!RpcStringFreeW` at `0x180183506`
- `RPCRT4!RpcStringFreeW` at `0x180183506`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1801834fa`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1801834fa`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(RPC_WSTR NetworkAddr, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  RPC_WSTR v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  size_t v11; // r15
  WCHAR *v12; // rax
  wchar_t *v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  __int64 v16; // r11
  const wchar_t *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int16 *v20; // rdx
  __int64 v21; // rdx
  unsigned __int16 *v22; // rax
  __int64 v23; // r9
  const wchar_t *v24; // rcx
  unsigned __int16 *v25; // rax
  __int64 v26; // r8
  unsigned __int16 *v27; // rcx
  RPC_STATUS v28; // ebx
  RPC_STATUS v29; // ebx
  int v30; // ecx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  String = 0;
  v5 = NetworkAddr;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !NetworkAddr )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( NetworkAddr[v7] );
  if ( !*NetworkAddr )
    goto LABEL_26;
  if ( *NetworkAddr == 92 )
  {
    if ( NetworkAddr[1] != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)NetworkAddr;
    if ( NetworkAddr == (RPC_WSTR)-4LL )
      goto LABEL_27;
    v5 = NetworkAddr + 2;
  }
  else
  {
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 6);
    v6 = v10;
    if ( !v10 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v10 = 6029404;
    memcpy_0(v10 + 2, v5, 2 * v7 + 2);
    v9 = (unsigned __int64)v6;
  }
  if ( v7 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v7 == nSize && !wcsnicmp(Buffer, v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( v5[v7 - 1] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(wcsnicmp(v13, v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v15 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_53;
  }
  v16 = 2147483646;
  v17 = L"\\PIPE\\";
  v18 = 2147483646;
  v19 = 14;
  do
  {
    if ( !v18 )
      break;
    if ( !*v17 )
      break;
    *v14++ = *v17++;
    --v18;
    --v19;
  }
  while ( v19 );
  v20 = v14 - 1;
  if ( v19 )
    v20 = v14;
  *v20 = 0;
  if ( v19 )
  {
    v21 = 14;
    v22 = v15;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v21;
    }
    while ( v21 );
    v23 = (14 - v21) & -(__int64)(v21 != 0);
    if ( v21 )
    {
      v24 = L"lsarpc";
      v25 = &v15[v23];
      v26 = 14 - v23;
      if ( 14 != v23 )
      {
        do
        {
          if ( !v16 )
            break;
          if ( !*v24 )
            break;
          *v25++ = *v24++;
          --v16;
          --v26;
        }
        while ( v26 );
      }
      v27 = v25 - 1;
      if ( v26 )
        v27 = v25;
      *v27 = 0;
      if ( v26 )
      {
        v28 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v15, 0, &String);
        LocalFree(v15);
        if ( !v28 )
        {
          v29 = RpcBindingFromStringBindingW(String, a4);
          RpcStringFreeW(&String);
          if ( v29 )
          {
            *a4 = 0;
            v30 = -1073741534;
            if ( (unsigned int)(v29 - 1706) > 1 )
              v30 = -1073741801;
            v8 = v30;
          }
          else
          {
            v8 = 0;
          }
          goto LABEL_53;
        }
        goto LABEL_21;
      }
    }
  }
  LocalFree(v15);
  v8 = -1073741811;
LABEL_53:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x180183260  mov     [rsp-38h+arg_8], rbx
0x180183265  push    rbp
0x180183266  push    rsi
0x180183267  push    rdi
0x180183268  push    r12
0x18018326a  push    r13
0x18018326c  push    r14
0x18018326e  push    r15
0x180183270  mov     rbp, rsp
0x180183273  sub     rsp, 70h
0x180183277  mov     rax, cs:__security_cookie
0x18018327e  xor     rax, rsp
0x180183281  mov     [rbp+var_10], rax
0x180183285  xor     r13d, r13d
0x180183288  mov     r12, r9
0x18018328b  mov     [rbp+String], r13
0x18018328f  mov     rdi, rcx
0x180183292  mov     [rbp+nSize], r13d
0x180183296  mov     r14d, r13d
0x180183299  mov     [r9], r13
0x18018329c  test    rcx, rcx
0x18018329f  jz      loc_1801833E0
0x1801832a5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801832a9  inc     rbx
0x1801832ac  cmp     [rcx+rbx*2], r13w
0x1801832b1  jnz     short loc_1801832A9
0x1801832b3  cmp     [rcx], r13w
0x1801832b7  jz      loc_1801833E0
0x1801832bd  mov     esi, 5Ch ; '\'
0x1801832c2  cmp     [rcx], si
0x1801832c5  jnz     short loc_1801832F2
0x1801832c7  cmp     [rcx+2], si
0x1801832cb  jnz     short loc_1801832D3
0x1801832cd  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1801832d1  jnz     short loc_1801832DD
0x1801832d3  mov     ebx, 0C0000122h
0x1801832d8  jmp     loc_18018354F
0x1801832dd  lea     rax, [rcx+4]
0x1801832e1  mov     rsi, rdi
0x1801832e4  test    rax, rax
0x1801832e7  jz      loc_1801833E3
0x1801832ed  mov     rdi, rax
0x1801832f0  jmp     short loc_180183331
0x1801832f2  lea     rdx, ds:6[rbx*2]; uBytes
0x1801832fa  xor     ecx, ecx; uFlags
0x1801832fc  call    cs:__imp_LocalAlloc
0x180183302  mov     r14, rax
0x180183305  test    rax, rax
0x180183308  jnz     short loc_180183314
0x18018330a  mov     ebx, 0C0000017h
0x18018330f  jmp     loc_18018354F
0x180183314  lea     r8, ds:2[rbx*2]; Size
0x18018331c  mov     dword ptr [rax], 5C005Ch
0x180183322  lea     rcx, [rax+4]; void *
0x180183326  mov     rdx, rdi; Src
0x180183329  call    memcpy_0
0x18018332e  mov     rsi, r14
0x180183331  cmp     rbx, 0Fh
0x180183335  ja      short loc_18018336D
0x180183337  lea     r8, [rbp+nSize]; nSize
0x18018333b  mov     [rbp+nSize], 10h
0x180183342  lea     rdx, [rbp+Buffer]; lpBuffer
0x180183346  xor     ecx, ecx; NameType
0x180183348  call    cs:__imp_GetComputerNameExW
0x18018334e  test    eax, eax
0x180183350  jz      short loc_18018336D
0x180183352  mov     eax, [rbp+nSize]
0x180183355  cmp     rbx, rax
0x180183358  jnz     short loc_18018336D
0x18018335a  mov     r8, rbx; MaxCount
0x18018335d  lea     rcx, [rbp+Buffer]; String1
0x180183361  mov     rdx, rdi; String2
0x180183364  call    _wcsnicmp
0x180183369  test    eax, eax
0x18018336b  jz      short loc_1801833E0
0x18018336d  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180183373  lea     r15, [rbx-1]
0x180183377  mov     edx, 20Ah; uBytes
0x18018337c  cmovnz  r15, rbx
0x180183380  xor     ecx, ecx; uFlags
0x180183382  call    cs:__imp_LocalAlloc
0x180183388  mov     rbx, rax
0x18018338b  test    rax, rax
0x18018338e  jnz     short loc_18018339A
0x180183390  mov     ebx, 0C0000017h
0x180183395  jmp     loc_180183541
0x18018339a  lea     r8, [rbp+nSize]; nSize
0x18018339e  mov     [rbp+nSize], 105h
0x1801833a5  mov     rdx, rbx; lpBuffer
0x1801833a8  mov     ecx, 3; NameType
0x1801833ad  call    cs:__imp_GetComputerNameExW
0x1801833b3  test    eax, eax
0x1801833b5  jz      short loc_1801833D5
0x1801833b7  mov     eax, [rbp+nSize]
0x1801833ba  cmp     r15, rax
0x1801833bd  jnz     short loc_1801833D5
0x1801833bf  mov     r8, r15; MaxCount
0x1801833c2  mov     rdx, rdi; String2
0x1801833c5  mov     rcx, rbx; String1
0x1801833c8  call    _wcsnicmp
0x1801833cd  neg     eax
0x1801833cf  sbb     rcx, rcx
0x1801833d2  and     rsi, rcx
0x1801833d5  mov     rcx, rbx; hMem
0x1801833d8  call    cs:__imp_LocalFree
0x1801833de  jmp     short loc_1801833E3
0x1801833e0  mov     rsi, r13
0x1801833e3  mov     edx, 1Ch; uBytes
0x1801833e8  xor     ecx, ecx; uFlags
0x1801833ea  call    cs:__imp_LocalAlloc
0x1801833f0  mov     rdi, rax
0x1801833f3  test    rax, rax
0x1801833f6  jz      short loc_180183390
0x1801833f8  mov     r11d, 7FFFFFFEh
0x1801833fe  lea     r9, aPipe; "\\PIPE\\"
0x180183405  mov     r8d, 0Eh
0x18018340b  mov     edx, r11d
0x18018340e  mov     ecx, r8d
0x180183411  test    rdx, rdx
0x180183414  jz      short loc_180183435
0x180183416  movzx   r10d, word ptr [r9]
0x18018341a  test    r10w, r10w
0x18018341e  jz      short loc_180183435
0x180183420  mov     [rax], r10w
0x180183424  add     r9, 2
0x180183428  add     rax, 2
0x18018342c  dec     rdx
0x18018342f  sub     rcx, 1
0x180183433  jnz     short loc_180183411
0x180183435  test    rcx, rcx
0x180183438  lea     rdx, [rax-2]
0x18018343c  cmovnz  rdx, rax
0x180183440  mov     [rdx], r13w
0x180183444  jz      loc_180183533
0x18018344a  mov     rdx, r8
0x18018344d  mov     rax, rdi
0x180183450  cmp     [rax], r13w
0x180183454  jz      short loc_180183460
0x180183456  add     rax, 2
0x18018345a  sub     rdx, 1
0x18018345e  jnz     short loc_180183450
0x180183460  mov     rcx, r8
0x180183463  mov     rax, rdx
0x180183466  sub     rcx, rdx
0x180183469  neg     rax
0x18018346c  sbb     r9, r9
0x18018346f  and     r9, rcx
0x180183472  test    rdx, rdx
0x180183475  jz      loc_180183533
0x18018347b  lea     rcx, aLsarpc; "lsarpc"
0x180183482  lea     rax, [rdi+r9*2]
0x180183486  sub     r8, r9
0x180183489  jz      short loc_1801834AC
0x18018348b  test    r11, r11
0x18018348e  jz      short loc_1801834AC
0x180183490  movzx   edx, word ptr [rcx]
0x180183493  test    dx, dx
0x180183496  jz      short loc_1801834AC
0x180183498  mov     [rax], dx
0x18018349b  add     rcx, 2
0x18018349f  add     rax, 2
0x1801834a3  dec     r11
0x1801834a6  sub     r8, 1
0x1801834aa  jnz     short loc_18018348B
0x1801834ac  test    r8, r8
0x1801834af  lea     rcx, [rax-2]
0x1801834b3  cmovnz  rcx, rax
0x1801834b7  mov     [rcx], r13w
0x1801834bb  jz      short loc_180183533
0x1801834bd  lea     rax, [rbp+String]
0x1801834c1  mov     r9, rdi; Endpoint
0x1801834c4  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1801834c9  lea     rdx, ProtSeq; "ncacn_np"
0x1801834d0  mov     r8, rsi; NetworkAddr
0x1801834d3  mov     [rsp+70h+Options], r13; Options
0x1801834d8  xor     ecx, ecx; ObjUuid
0x1801834da  call    cs:__imp_RpcStringBindingComposeW
0x1801834e0  mov     rcx, rdi; hMem
0x1801834e3  mov     ebx, eax
0x1801834e5  call    cs:__imp_LocalFree
0x1801834eb  test    ebx, ebx
0x1801834ed  jnz     loc_180183390
0x1801834f3  mov     rcx, [rbp+String]; StringBinding
0x1801834f7  mov     rdx, r12; Binding
0x1801834fa  call    cs:__imp_RpcBindingFromStringBindingW
0x180183500  lea     rcx, [rbp+String]; String
0x180183504  mov     ebx, eax
0x180183506  call    cs:__imp_RpcStringFreeW
0x18018350c  test    ebx, ebx
0x18018350e  jz      short loc_18018352E
0x180183510  lea     eax, [rbx-6AAh]
0x180183516  mov     [r12], r13
0x18018351a  mov     ebx, 0C0000017h
0x18018351f  cmp     eax, 1
0x180183522  mov     ecx, 0C0000122h
0x180183527  cmova   ecx, ebx
0x18018352a  mov     ebx, ecx
0x18018352c  jmp     short loc_180183541
0x18018352e  mov     ebx, r13d
0x180183531  jmp     short loc_180183541
0x180183533  mov     rcx, rdi; hMem
0x180183536  call    cs:__imp_LocalFree
0x18018353c  mov     ebx, 0C000000Dh
0x180183541  test    r14, r14
0x180183544  jz      short loc_18018354F
0x180183546  mov     rcx, r14; hMem
0x180183549  call    cs:__imp_LocalFree
0x18018354f  mov     eax, ebx
0x180183551  mov     rcx, [rbp+var_10]
0x180183555  xor     rcx, rsp; StackCookie
0x180183558  call    __security_check_cookie
0x18018355d  mov     rbx, [rsp+70h+arg_8]
0x180183565  add     rsp, 70h
0x180183569  pop     r15
0x18018356b  pop     r14
0x18018356d  pop     r13
0x18018356f  pop     r12
0x180183571  pop     rdi
0x180183572  pop     rsi
0x180183573  pop     rbp
0x180183574  retn
```
