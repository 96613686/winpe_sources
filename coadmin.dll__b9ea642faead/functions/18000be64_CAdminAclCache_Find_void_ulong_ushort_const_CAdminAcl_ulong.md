# CAdminAclCache::_Find(void *,ulong,ushort const *,CAdminAcl * *,ulong *)

- ea: `0x18000be64`
- end: `0x18000bf8f`
- name: `?_Find@CAdminAclCache@@AEAAJPEAXKPEBGPEAPEAVCAdminAcl@@PEAK@Z`
- size: `299`
- prototype: `int(CAdminAclCache *__hidden this, void *, unsigned int, const unsigned __int16 *, struct CAdminAcl **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000aefc`
- `0x18000b1e4`

## callees

- `0x18000be64`
- `0x18000bf98`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000bf3e`
- `msvcrt!_wcsicmp` at `0x18000bf3e`

## pseudocode

```c
__int64 __fastcall CAdminAclCache::_Find(
        CAdminAclCache *this,
        void *a2,
        int a3,
        const unsigned __int16 *a4,
        struct CAdminAcl **a5,
        unsigned int *a6)
{
  struct CAdminAcl **v6; // r14
  int v8; // ebx
  unsigned int *v9; // rsi
  const wchar_t *v10; // rbp
  unsigned int v11; // edi
  int v12; // r12d
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  volatile signed __int32 *v16; // rax
  int v17; // [rsp+60h] [rbp+8h] BYREF
  int v18; // [rsp+64h] [rbp+Ch]
  void *v19; // [rsp+68h] [rbp+10h]

  v19 = a2;
  v18 = HIDWORD(this);
  v6 = a5;
  v17 = 0;
  if ( a5 )
  {
    v8 = 0;
    *a5 = 0;
  }
  else
  {
    v8 = -2147024809;
  }
  v9 = a6;
  if ( a6 )
  {
    *a6 = 0;
    if ( v8 >= 0 )
    {
      v10 = &byte_1800127D8;
      if ( a4 )
        v10 = a4;
      v8 = HashString(v10, &v17);
      if ( v8 >= 0 )
      {
        v11 = 0;
        if ( !dword_1800160F4 )
          return 1;
        v12 = v17;
        while ( 1 )
        {
          v13 = &byte_1800127D8;
          v14 = *(_QWORD *)&g_AclCache[2 * v11 + 2];
          if ( v14 != -4 )
            v13 = (const wchar_t *)(v14 + 4);
          if ( *(void **)(v14 + 552) == v19
            && *(_DWORD *)(v14 + 528) == a3
            && *(_DWORD *)(v14 + 524) == v12
            && !_wcsicmp(v13, v10) )
          {
            break;
          }
          if ( ++v11 >= dword_1800160F4 )
            return 1;
        }
        v16 = *(volatile signed __int32 **)&g_AclCache[2 * v11 + 2];
        if ( v16 )
        {
          _InterlockedIncrement(v16 + 142);
          *v6 = (struct CAdminAcl *)v16;
          *v9 = v11;
        }
        else
        {
          return 1;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000be64  mov     rax, rsp
0x18000be67  mov     [rax+18h], rbx
0x18000be6b  mov     [rax+10h], rdx
0x18000be6f  mov     [rax+8], rcx
0x18000be73  push    rbp
0x18000be74  push    rsi
0x18000be75  push    rdi
0x18000be76  push    r12
0x18000be78  push    r13
0x18000be7a  push    r14
0x18000be7c  push    r15
0x18000be7e  sub     rsp, 20h
0x18000be82  mov     r14, [rsp+58h+arg_20]
0x18000be8a  xor     r15d, r15d
0x18000be8d  mov     [rax+8], r15d
0x18000be91  mov     eax, 80070057h
0x18000be96  mov     r13d, r8d
0x18000be99  test    r14, r14
0x18000be9c  jnz     short loc_18000BEA2
0x18000be9e  mov     ebx, eax
0x18000bea0  jmp     short loc_18000BEA8
0x18000bea2  mov     ebx, r15d
0x18000bea5  mov     [r14], r15
0x18000bea8  mov     rsi, [rsp+58h+arg_28]
0x18000beb0  test    rsi, rsi
0x18000beb3  jnz     short loc_18000BEBC
0x18000beb5  mov     ebx, eax
0x18000beb7  jmp     loc_18000BF59
0x18000bebc  mov     [rsi], r15d
0x18000bebf  test    ebx, ebx
0x18000bec1  js      loc_18000BF59
0x18000bec7  test    r9, r9
0x18000beca  lea     rbp, byte_1800127D8
0x18000bed1  lea     rdx, [rsp+58h+arg_0]
0x18000bed6  cmovnz  rbp, r9
0x18000beda  mov     rcx, rbp
0x18000bedd  call    _HashString
0x18000bee2  mov     ebx, eax
0x18000bee4  test    eax, eax
0x18000bee6  js      short loc_18000BF59
0x18000bee8  mov     ecx, cs:dword_1800160F4
0x18000beee  mov     edi, r15d
0x18000bef1  test    ecx, ecx
0x18000bef3  jz      short loc_18000BF54
0x18000bef5  mov     r12d, [rsp+58h+arg_0]
0x18000befa  lea     rax, ?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000bf01  mov     r15d, edi
0x18000bf04  lea     rcx, byte_1800127D8
0x18000bf0b  mov     rdx, [rax+r15*8+8]
0x18000bf10  lea     rax, [rdx+4]
0x18000bf14  test    rax, rax
0x18000bf17  cmovnz  rcx, rax; String1
0x18000bf1b  mov     rax, [rsp+58h+arg_8]
0x18000bf20  cmp     [rdx+228h], rax
0x18000bf27  jnz     short loc_18000BF48
0x18000bf29  cmp     [rdx+210h], r13d
0x18000bf30  jnz     short loc_18000BF48
0x18000bf32  cmp     [rdx+20Ch], r12d
0x18000bf39  jnz     short loc_18000BF48
0x18000bf3b  mov     rdx, rbp; String2
0x18000bf3e  call    cs:__imp__wcsicmp
0x18000bf44  test    eax, eax
0x18000bf46  jz      short loc_18000BF70
0x18000bf48  mov     eax, cs:dword_1800160F4
0x18000bf4e  inc     edi
0x18000bf50  cmp     edi, eax
0x18000bf52  jb      short loc_18000BEFA
0x18000bf54  mov     ebx, 1
0x18000bf59  mov     eax, ebx
0x18000bf5b  mov     rbx, [rsp+58h+arg_10]
0x18000bf60  add     rsp, 20h
0x18000bf64  pop     r15
0x18000bf66  pop     r14
0x18000bf68  pop     r13
0x18000bf6a  pop     r12
0x18000bf6c  pop     rdi
0x18000bf6d  pop     rsi
0x18000bf6e  pop     rbp
0x18000bf6f  retn
0x18000bf70  lea     rax, ?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000bf77  mov     rax, [rax+r15*8+8]
0x18000bf7c  test    rax, rax
0x18000bf7f  jz      short loc_18000BF54
0x18000bf81  lock inc dword ptr [rax+238h]
0x18000bf88  mov     [r14], rax
0x18000bf8b  mov     [rsi], edi
0x18000bf8d  jmp     short loc_18000BF59
```
