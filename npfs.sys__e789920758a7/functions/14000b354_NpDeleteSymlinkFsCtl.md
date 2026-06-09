# NpDeleteSymlinkFsCtl

- ea: `0x14000b354`
- end: `0x14000b543`
- name: `NpDeleteSymlinkFsCtl`
- size: `495`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x14000efb0`

## callees

- `0x140001e10`
- `0x140002240`
- `0x14000b354`
- `0x14000c548`
- `0x14000c648`
- `0x140012730`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b458`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b458`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b470`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b470`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b4ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b4ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b4f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b4f6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b40b`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b40b`
- `ntoskrnl!SeCreateAccessState` at `0x14000b429`
- `ntoskrnl!SeCreateAccessState` at `0x14000b429`
- `ntoskrnl!SeDeleteAccessState` at `0x14000b507`
- `ntoskrnl!SeDeleteAccessState` at `0x14000b507`

## pseudocode

```c
__int64 __fastcall NpDeleteSymlinkFsCtl(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r14
  unsigned int v7; // edx
  int AccessState; // ebx
  unsigned __int16 *v9; // rdi
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  _WORD *Prefix; // rdi
  _WORD v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  char *v19; // [rsp+28h] [rbp-D8h]
  __int128 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[160]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[224]; // [rsp+E0h] [rbp-20h] BYREF

  memset(v21, 0, sizeof(v21));
  memset(v22, 0, sizeof(v22));
  v4 = *(_QWORD *)(a2 + 184);
  v18 = 0;
  v20 = 0;
  v5 = *(_QWORD *)(v4 + 48);
  if ( **(_WORD **)(v5 + 24) == 513 && (v6 = *(_QWORD *)(a1 + 64), (*(_QWORD *)(v5 + 32) & 1) != 0) )
  {
    v7 = *(_DWORD *)(v4 + 16);
    if ( v7 < 4 )
      return (unsigned int)-1073741811;
    v9 = *(unsigned __int16 **)(a2 + 24);
    if ( *v9 + (unsigned int)v9[1] > v7 )
    {
      return (unsigned int)-1073741811;
    }
    else
    {
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      AccessState = SeCreateAccessState(v21, v22, 0x10000, FileObjectGenericMapping);
      if ( AccessState >= 0 )
      {
        v19 = (char *)v9 + *v9;
        v17[0] = v9[1];
        v17[1] = v17[0];
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v6 + 192, 0, v11, v12);
        LOBYTE(v13) = 1;
        Prefix = (_WORD *)NpFindPrefix(v6, v17, v13, &v20);
        if ( !Prefix || (_WORD)v20 )
        {
          AccessState = -1073741772;
        }
        else if ( *Prefix == 519 )
        {
          LOBYTE(v14) = *(_BYTE *)(a2 + 64);
          AccessState = NpDeleteSymlinkAccessCheck(Prefix, v14, v21);
          if ( AccessState >= 0 )
          {
            NpDeleteSymlink(Prefix);
            AccessState = 0;
            *(_QWORD *)(a2 + 56) = 0;
          }
        }
        else
        {
          AccessState = -1073741773;
        }
        ExReleasePushLockExclusiveEx(v6 + 192, 0);
        KeLeaveCriticalRegion();
        SeDeleteAccessState(v21);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741649;
  }
  return (unsigned int)AccessState;
}

```

## disassembly

```asm
0x14000b354  mov     [rsp-8+arg_10], rbx
0x14000b359  push    rbp
0x14000b35a  push    rsi
0x14000b35b  push    rdi
0x14000b35c  push    r14
0x14000b35e  push    r15
0x14000b360  lea     rbp, [rsp-0D0h]
0x14000b368  sub     rsp, 1D0h
0x14000b36f  mov     rax, cs:__security_cookie
0x14000b376  xor     rax, rsp
0x14000b379  mov     [rbp+0F0h+var_30], rax
0x14000b380  mov     rsi, rdx
0x14000b383  mov     r14, rcx
0x14000b386  xor     edx, edx; Val
0x14000b388  lea     rcx, [rsp+1F0h+var_1B0]; void *
0x14000b38d  mov     r8d, 0A0h; Size
0x14000b393  call    memset
0x14000b398  xor     edx, edx; Val
0x14000b39a  lea     rcx, [rbp+0F0h+var_110]; void *
0x14000b39e  mov     r8d, 0E0h; Size
0x14000b3a4  call    memset
0x14000b3a9  mov     rdx, [rsi+0B8h]
0x14000b3b0  mov     r8d, 201h
0x14000b3b6  xorps   xmm0, xmm0
0x14000b3b9  mov     [rsp+1F0h+var_1CC], 0
0x14000b3c1  movups  [rsp+1F0h+var_1C0], xmm0
0x14000b3c6  mov     rcx, [rdx+30h]
0x14000b3ca  mov     rax, [rcx+18h]
0x14000b3ce  cmp     [rax], r8w
0x14000b3d2  jnz     loc_14000B515
0x14000b3d8  mov     rax, [rcx+20h]
0x14000b3dc  mov     r14, [r14+40h]
0x14000b3e0  test    al, 1
0x14000b3e2  jz      loc_14000B515
0x14000b3e8  mov     edx, [rdx+10h]
0x14000b3eb  cmp     edx, 4
0x14000b3ee  jnb     short loc_14000B3FA
0x14000b3f0  mov     ebx, 0C000000Dh
0x14000b3f5  jmp     loc_14000B51A
0x14000b3fa  mov     rdi, [rsi+18h]
0x14000b3fe  movzx   ecx, word ptr [rdi+2]
0x14000b402  movzx   eax, word ptr [rdi]
0x14000b405  add     ecx, eax
0x14000b407  cmp     ecx, edx
0x14000b409  ja      short loc_14000B3F0
0x14000b40b  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000b412  nop     dword ptr [rax+rax+00h]
0x14000b417  mov     r8d, 10000h
0x14000b41d  lea     rdx, [rbp+0F0h+var_110]
0x14000b421  mov     r9, rax
0x14000b424  lea     rcx, [rsp+1F0h+var_1B0]
0x14000b429  call    cs:__imp_SeCreateAccessState
0x14000b430  nop     dword ptr [rax+rax+00h]
0x14000b435  mov     ebx, eax
0x14000b437  test    eax, eax
0x14000b439  js      loc_14000B51A
0x14000b43f  movzx   eax, word ptr [rdi]
0x14000b442  add     rax, rdi
0x14000b445  mov     [rsp+1F0h+var_1C8], rax
0x14000b44a  movzx   eax, word ptr [rdi+2]
0x14000b44e  mov     [rsp+1F0h+var_1D0], ax
0x14000b453  mov     [rsp+1F0h+var_1CE], ax
0x14000b458  call    cs:__imp_KeEnterCriticalRegion
0x14000b45f  nop     dword ptr [rax+rax+00h]
0x14000b464  lea     r15, [r14+0C0h]
0x14000b46b  xor     edx, edx
0x14000b46d  mov     rcx, r15
0x14000b470  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b477  nop     dword ptr [rax+rax+00h]
0x14000b47c  lea     r9, [rsp+1F0h+var_1C0]
0x14000b481  mov     r8b, 1
0x14000b484  lea     rdx, [rsp+1F0h+var_1D0]
0x14000b489  mov     rcx, r14
0x14000b48c  call    NpFindPrefix
0x14000b491  mov     rdi, rax
0x14000b494  test    rax, rax
0x14000b497  jz      short loc_14000B4E0
0x14000b499  xor     ecx, ecx
0x14000b49b  cmp     cx, word ptr [rsp+1F0h+var_1C0]
0x14000b4a0  jnz     short loc_14000B4E0
0x14000b4a2  mov     eax, 207h
0x14000b4a7  cmp     [rdi], ax
0x14000b4aa  jz      short loc_14000B4B3
0x14000b4ac  mov     ebx, 0C0000033h
0x14000b4b1  jmp     short loc_14000B4E5
0x14000b4b3  mov     dl, [rsi+40h]
0x14000b4b6  lea     r8, [rsp+1F0h+var_1B0]
0x14000b4bb  mov     rcx, rdi
0x14000b4be  call    NpDeleteSymlinkAccessCheck
0x14000b4c3  mov     ebx, eax
0x14000b4c5  test    eax, eax
0x14000b4c7  js      short loc_14000B4E5
0x14000b4c9  mov     rdx, r14
0x14000b4cc  mov     rcx, rdi; P
0x14000b4cf  call    NpDeleteSymlink
0x14000b4d4  xor     ebx, ebx
0x14000b4d6  mov     qword ptr [rsi+38h], 0
0x14000b4de  jmp     short loc_14000B4E5
0x14000b4e0  mov     ebx, 0C0000034h
0x14000b4e5  xor     edx, edx
0x14000b4e7  mov     rcx, r15
0x14000b4ea  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b4f1  nop     dword ptr [rax+rax+00h]
0x14000b4f6  call    cs:__imp_KeLeaveCriticalRegion
0x14000b4fd  nop     dword ptr [rax+rax+00h]
0x14000b502  lea     rcx, [rsp+1F0h+var_1B0]
0x14000b507  call    cs:__imp_SeDeleteAccessState
0x14000b50e  nop     dword ptr [rax+rax+00h]
0x14000b513  jmp     short loc_14000B51A
0x14000b515  mov     ebx, 0C00000AFh
0x14000b51a  mov     eax, ebx
0x14000b51c  mov     rcx, [rbp+0F0h+var_30]
0x14000b523  xor     rcx, rsp; StackCookie
0x14000b526  call    __security_check_cookie
0x14000b52b  mov     rbx, [rsp+1F0h+arg_10]
0x14000b533  add     rsp, 1D0h
0x14000b53a  pop     r15
0x14000b53c  pop     r14
0x14000b53e  pop     rdi
0x14000b53f  pop     rsi
0x14000b540  pop     rbp
0x14000b541  retn
```
