# SipcPrivateNamespace::Open(SipcPrivateNamespaceAttributes const &)

- ea: `0x180142ffc`
- end: `0x180143134`
- name: `?Open@SipcPrivateNamespace@@QEAAJAEBUSipcPrivateNamespaceAttributes@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this, const struct SipcPrivateNamespaceAttributes *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a32c0`

## callees

- `0x18014265c`
- `0x180142ffc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801430e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801430e4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180143010`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180143022`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180143010`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180143022`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x1801430d6`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x1801430d6`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1801430c0`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180143108`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18014311a`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1801430c0`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180143108`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18014311a`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::Open(
        SipcPrivateNamespace *this,
        const struct SipcPrivateNamespaceAttributes *a2)
{
  __int128 v4; // xmm0
  int BoundaryDescriptorAndInitializeName; // ebx
  HANDLE v7; // rbx
  HANDLE v8; // rax
  signed int LastError; // eax
  unsigned int v10; // edi
  HANDLE BoundaryDescriptor; // [rsp+38h] [rbp+10h] BYREF

  if ( !IsValidSid((char *)a2 + 16) || !IsValidSid((char *)a2 + 84) )
    return 2147942487LL;
  v4 = *(_OWORD *)a2;
  BoundaryDescriptor = 0;
  *(_OWORD *)((char *)this + 84) = v4;
  *(_OWORD *)((char *)this + 100) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 116) = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 132) = *((_OWORD *)a2 + 3);
  *(_OWORD *)((char *)this + 148) = *((_OWORD *)a2 + 4);
  *(_OWORD *)((char *)this + 164) = *((_OWORD *)a2 + 5);
  *(_OWORD *)((char *)this + 180) = *((_OWORD *)a2 + 6);
  *(_OWORD *)((char *)this + 196) = *((_OWORD *)a2 + 7);
  *(_OWORD *)((char *)this + 212) = *((_OWORD *)a2 + 8);
  *(_QWORD *)((char *)this + 228) = *((_QWORD *)a2 + 18);
  BoundaryDescriptorAndInitializeName = SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(
                                          this,
                                          &BoundaryDescriptor);
  if ( BoundaryDescriptorAndInitializeName >= 0 )
  {
    v7 = BoundaryDescriptor;
    v8 = OpenPrivateNamespaceW(BoundaryDescriptor, (LPCWSTR)this + 4);
    *(_QWORD *)this = v8;
    if ( v8 )
    {
      if ( v7 )
        DeleteBoundaryDescriptor(v7);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = -2147418113;
      if ( LastError < 0 )
        v10 = LastError;
      if ( v7 )
        DeleteBoundaryDescriptor(v7);
      return v10;
    }
  }
  else
  {
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    return (unsigned int)BoundaryDescriptorAndInitializeName;
  }
}

```

## disassembly

```asm
0x180142ffc  mov     [rsp+arg_0], rbx
0x180143001  push    rdi
0x180143002  sub     rsp, 20h
0x180143006  mov     rdi, rcx
0x180143009  mov     rbx, rdx
0x18014300c  lea     rcx, [rdx+10h]; pSid
0x180143010  call    cs:__imp_IsValidSid
0x180143016  test    eax, eax
0x180143018  jz      loc_180143124
0x18014301e  lea     rcx, [rbx+54h]; pSid
0x180143022  call    cs:__imp_IsValidSid
0x180143028  test    eax, eax
0x18014302a  jz      loc_180143124
0x180143030  movups  xmm0, xmmword ptr [rbx]
0x180143033  lea     rdx, [rsp+28h+BoundaryDescriptor]; void **
0x180143038  mov     [rsp+28h+BoundaryDescriptor], 0
0x180143041  mov     rcx, rdi; this
0x180143044  movups  xmmword ptr [rdi+54h], xmm0
0x180143048  movups  xmm1, xmmword ptr [rbx+10h]
0x18014304c  movups  xmmword ptr [rdi+64h], xmm1
0x180143050  movups  xmm0, xmmword ptr [rbx+20h]
0x180143054  movups  xmmword ptr [rdi+74h], xmm0
0x180143058  movups  xmm1, xmmword ptr [rbx+30h]
0x18014305c  movups  xmmword ptr [rdi+84h], xmm1
0x180143063  movups  xmm0, xmmword ptr [rbx+40h]
0x180143067  movups  xmmword ptr [rdi+94h], xmm0
0x18014306e  movups  xmm1, xmmword ptr [rbx+50h]
0x180143072  movups  xmmword ptr [rdi+0A4h], xmm1
0x180143079  movups  xmm0, xmmword ptr [rbx+60h]
0x18014307d  movups  xmmword ptr [rdi+0B4h], xmm0
0x180143084  movups  xmm1, xmmword ptr [rbx+70h]
0x180143088  movups  xmmword ptr [rdi+0C4h], xmm1
0x18014308f  movups  xmm0, xmmword ptr [rbx+80h]
0x180143096  movups  xmmword ptr [rdi+0D4h], xmm0
0x18014309d  mov     rax, [rbx+90h]
0x1801430a4  mov     [rdi+0E4h], rax
0x1801430ab  call    ?GetBoundaryDescriptorAndInitializeName@SipcPrivateNamespace@@AEAAJPEAPEAX@Z; SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(void * *)
0x1801430b0  mov     ebx, eax
0x1801430b2  test    eax, eax
0x1801430b4  jns     short loc_1801430CA
0x1801430b6  mov     rcx, [rsp+28h+BoundaryDescriptor]; BoundaryDescriptor
0x1801430bb  test    rcx, rcx
0x1801430be  jz      short loc_1801430C6
0x1801430c0  call    cs:__imp_DeleteBoundaryDescriptor
0x1801430c6  mov     eax, ebx
0x1801430c8  jmp     short loc_180143129
0x1801430ca  mov     rbx, [rsp+28h+BoundaryDescriptor]
0x1801430cf  lea     rdx, [rdi+8]; lpAliasPrefix
0x1801430d3  mov     rcx, rbx; lpBoundaryDescriptor
0x1801430d6  call    cs:__imp_OpenPrivateNamespaceW
0x1801430dc  mov     [rdi], rax
0x1801430df  test    rax, rax
0x1801430e2  jnz     short loc_180143112
0x1801430e4  call    cs:__imp_GetLastError
0x1801430ea  test    eax, eax
0x1801430ec  jle     short loc_1801430F6
0x1801430ee  movzx   eax, ax
0x1801430f1  or      eax, 80070000h
0x1801430f6  test    eax, eax
0x1801430f8  mov     edi, 8000FFFFh
0x1801430fd  cmovs   edi, eax
0x180143100  test    rbx, rbx
0x180143103  jz      short loc_18014310E
0x180143105  mov     rcx, rbx; BoundaryDescriptor
0x180143108  call    cs:__imp_DeleteBoundaryDescriptor
0x18014310e  mov     eax, edi
0x180143110  jmp     short loc_180143129
0x180143112  test    rbx, rbx
0x180143115  jz      short loc_180143120
0x180143117  mov     rcx, rbx; BoundaryDescriptor
0x18014311a  call    cs:__imp_DeleteBoundaryDescriptor
0x180143120  xor     eax, eax
0x180143122  jmp     short loc_180143129
0x180143124  mov     eax, 80070057h
0x180143129  mov     rbx, [rsp+28h+arg_0]
0x18014312e  add     rsp, 20h
0x180143132  pop     rdi
0x180143133  retn
```
