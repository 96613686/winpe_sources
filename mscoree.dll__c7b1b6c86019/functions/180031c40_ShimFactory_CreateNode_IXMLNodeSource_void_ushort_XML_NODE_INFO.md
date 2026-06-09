# ShimFactory::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x180031c40`
- end: `0x180031faa`
- name: `?CreateNode@ShimFactory@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `874`
- prototype: `__int64 __usercall@<rax>(ShimFactory *__hidden this@<rcx>, struct IXMLNodeSource *@<rdx>, void *@<r8>, unsigned __int16@<r9w>, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003840`
- `0x180031a48`
- `0x180031b7c`
- `0x180031c40`
- `0x18003203c`
- `0x18003248c`

## pseudocode

```c
__int64 __fastcall ShimFactory::CreateNode(
        ShimFactory *this,
        struct IXMLNodeSource *a2,
        void *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  struct _XML_NODE_INFO **v5; // r13
  unsigned __int16 *v7; // rsi
  unsigned int v8; // r10d
  unsigned int v9; // r15d
  int v10; // ebp
  __int64 v11; // rax
  unsigned int v12; // r12d
  struct _XML_NODE_INFO *v13; // rdx
  int v14; // ecx
  unsigned int v15; // edi
  const unsigned __int16 *i; // r14
  unsigned __int16 v17; // dx
  __int64 v18; // r8
  unsigned __int16 v19; // dx
  int v20; // ecx
  int v21; // ecx
  __int64 result; // rax
  void *v23; // rcx
  int v24; // esi
  bool v25; // zf
  unsigned __int16 *v26; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+20h] BYREF

  v5 = a5;
  if ( *((_DWORD *)*a5 + 1) == 1 )
    ++*((_DWORD *)this + 18);
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v27 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  LODWORD(a5) = a4;
  while ( (unsigned int)v11 < v8 )
  {
    v13 = v5[v11];
    v14 = *((_DWORD *)v13 + 1);
    if ( (unsigned int)(v14 - 1) > 1 && v14 != 13 )
      goto LABEL_64;
    v15 = *((_DWORD *)v13 + 6);
    for ( i = (const unsigned __int16 *)*((_QWORD *)v13 + 2); ; ++i )
    {
      v17 = *i;
      if ( !*i || (unsigned __int16)(v17 - 9) > 4u && v17 != 32 )
        break;
      if ( !v15 )
        goto LABEL_17;
      --v15;
    }
    if ( v15 )
    {
      do
      {
        v18 = v15 - 1;
        v19 = i[v18];
        if ( (unsigned __int16)(v19 - 9) > 4u && v19 != 32 )
          break;
        --v15;
      }
      while ( (_DWORD)v18 );
    }
LABEL_17:
    v20 = v14 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        if ( v21 != 11 )
          goto LABEL_64;
        if ( *((_DWORD *)this + 13) != 1 )
          goto LABEL_36;
        v26 = 0;
        if ( (unsigned int)(v10 - 1) <= 1 )
        {
          result = ExtractXMLVersionAttribute(v5, v8, &v27, &v26);
          v9 = result;
          if ( (int)result < 0 )
            return result;
          v12 = v27;
          v7 = v26;
        }
        if ( *((_DWORD *)this + 19) == 6 )
        {
          if ( v10 == 1 )
          {
            v9 = ShimFactory::AddSupportedVersion(this, v7);
LABEL_27:
            v7 = 0;
            goto LABEL_64;
          }
LABEL_33:
          if ( v10 == 2 )
          {
            *((_QWORD *)this + 3) = v7;
            v7 = 0;
            v9 = 0;
          }
          else
          {
            v7 = 0;
          }
LABEL_36:
          if ( *((_DWORD *)this + 14) == 1 && *((_DWORD *)this + 19) == 9 && v10 == 10 )
            v9 = ShimFactory::CopyBuildFlavor(this, i, v15);
          goto LABEL_64;
        }
        if ( *((_DWORD *)this + 19) != 5 || v10 != 1 )
          goto LABEL_33;
        v23 = (void *)*((_QWORD *)this + 2);
        if ( v23 )
          operator delete(v23);
        *((_QWORD *)this + 2) = v7;
        v7 = 0;
        v9 = 0;
      }
      else
      {
        if ( *((_DWORD *)this + 13) == 1 )
        {
          v24 = *((_DWORD *)this + 19);
          if ( (unsigned int)(v24 - 5) <= 1 && !XMLStringCompare(i, v15, L"version", 7u) )
          {
            v10 = 1;
            goto LABEL_27;
          }
          v10 = 0;
          if ( v24 == 5 )
          {
            v7 = 0;
            if ( !XMLStringCompare(i, v15, L"imageVersion", 0xCu) )
            {
              v10 = 2;
              goto LABEL_64;
            }
          }
          else
          {
            v7 = 0;
          }
        }
        if ( *((_DWORD *)this + 14) == 1 )
        {
          v10 = 0;
          if ( *((_DWORD *)this + 19) == 9 && !XMLStringCompare(i, v15, L"enabled", 7u) )
            v10 = 10;
        }
      }
    }
    else
    {
      v25 = *((_DWORD *)this + 13) == 1;
      *((_DWORD *)this + 19) = 0;
      if ( !v25 )
        goto LABEL_68;
      if ( !XMLStringCompare(i, v15, L"requiredRuntime", 0xFu) )
      {
        *((_DWORD *)this + 19) = 5;
        goto LABEL_64;
      }
      if ( XMLStringCompare(i, v15, L"supportedRuntime", 0x10u) )
      {
LABEL_68:
        if ( *((_DWORD *)this + 14) != 1 || XMLStringCompare(i, v15, L"gcServer", 8u) )
        {
          if ( XMLStringCompare(i, v15, L"startup", 7u) )
          {
            if ( !XMLStringCompare(i, v15, L"runtime", 7u) )
            {
              *((_DWORD *)this + 14) = 1;
              *((_DWORD *)this + 19) = 8;
            }
          }
          else
          {
            *((_DWORD *)this + 13) = 1;
            *((_DWORD *)this + 19) = 7;
          }
        }
        else
        {
          *((_DWORD *)this + 19) = 9;
        }
      }
      else
      {
        *((_DWORD *)this + 19) = 6;
      }
    }
LABEL_64:
    v8 = (unsigned int)a5;
    v27 = ++v12;
    v11 = v12;
  }
  return v9;
}

```

## disassembly

```asm
0x180031c40  push    rbx
0x180031c42  push    rbp
0x180031c43  push    rsi
0x180031c44  push    rdi
0x180031c45  push    r12
0x180031c47  push    r13
0x180031c49  push    r14
0x180031c4b  push    r15
0x180031c4d  sub     rsp, 38h
0x180031c51  mov     r13, [rsp+78h+arg_20]
0x180031c59  mov     rbx, rcx
0x180031c5c  mov     rax, [r13+0]
0x180031c60  cmp     dword ptr [rax+4], 1
0x180031c64  jnz     short loc_180031C69
0x180031c66  inc     dword ptr [rcx+48h]
0x180031c69  xor     esi, esi
0x180031c6b  movzx   r10d, r9w
0x180031c6f  mov     r15d, esi
0x180031c72  mov     [rsp+78h+arg_18], esi
0x180031c79  mov     ebp, esi
0x180031c7b  mov     eax, esi
0x180031c7d  mov     r12d, esi
0x180031c80  mov     dword ptr [rsp+78h+arg_20], r10d
0x180031c88  lea     r9d, [rsi+9]
0x180031c8c  cmp     eax, r10d
0x180031c8f  jnb     loc_180031F96
0x180031c95  mov     rdx, [r13+rax*8+0]
0x180031c9a  mov     ecx, [rdx+4]
0x180031c9d  lea     eax, [rcx-1]
0x180031ca0  cmp     eax, 1
0x180031ca3  jbe     short loc_180031CAE
0x180031ca5  cmp     ecx, 0Dh
0x180031ca8  jnz     loc_180031F7B
0x180031cae  mov     edi, [rdx+18h]
0x180031cb1  mov     r14, [rdx+10h]
0x180031cb5  jmp     short loc_180031CD4
0x180031cb7  movzx   eax, dx
0x180031cba  sub     ax, r9w
0x180031cbe  cmp     ax, 4
0x180031cc2  jbe     short loc_180031CCA
0x180031cc4  cmp     dx, 20h ; ' '
0x180031cc8  jnz     short loc_180031CDD
0x180031cca  test    edi, edi
0x180031ccc  jz      short loc_180031D05
0x180031cce  add     r14, 2
0x180031cd2  dec     edi
0x180031cd4  movzx   edx, word ptr [r14]
0x180031cd8  test    dx, dx
0x180031cdb  jnz     short loc_180031CB7
0x180031cdd  test    edi, edi
0x180031cdf  jz      short loc_180031D05
0x180031ce1  lea     r8d, [rdi-1]
0x180031ce5  movzx   edx, word ptr [r14+r8*2]
0x180031cea  movzx   eax, dx
0x180031ced  sub     ax, r9w
0x180031cf1  cmp     ax, 4
0x180031cf5  jbe     short loc_180031CFD
0x180031cf7  cmp     dx, 20h ; ' '
0x180031cfb  jnz     short loc_180031D05
0x180031cfd  mov     edi, r8d
0x180031d00  test    r8d, r8d
0x180031d03  jnz     short loc_180031CE1
0x180031d05  sub     ecx, 1
0x180031d08  jz      loc_180031EA2
0x180031d0e  sub     ecx, 1
0x180031d11  jz      loc_180031DF9
0x180031d17  cmp     ecx, 0Bh
0x180031d1a  jnz     loc_180031F7B
0x180031d20  cmp     dword ptr [rbx+34h], 1
0x180031d24  jnz     loc_180031DC6
0x180031d2a  lea     eax, [rbp-1]
0x180031d2d  mov     [rsp+78h+var_58], rsi
0x180031d32  cmp     eax, 1
0x180031d35  ja      short loc_180031D6D
0x180031d37  lea     r9, [rsp+78h+var_58]; unsigned __int16 **
0x180031d3c  mov     edx, r10d; unsigned int
0x180031d3f  lea     r8, [rsp+78h+arg_18]; unsigned int *
0x180031d47  mov     rcx, r13; struct _XML_NODE_INFO **
0x180031d4a  call    ?ExtractXMLVersionAttribute@@YAJPEAPEAU_XML_NODE_INFO@@KPEAKPEAPEAG@Z; ExtractXMLVersionAttribute(_XML_NODE_INFO * *,ulong,ulong *,ushort * *)
0x180031d4f  mov     r15d, eax
0x180031d52  test    eax, eax
0x180031d54  js      loc_180031F99
0x180031d5a  mov     r12d, [rsp+78h+arg_18]
0x180031d62  mov     r9d, 9
0x180031d68  mov     rsi, [rsp+78h+var_58]
0x180031d6d  cmp     dword ptr [rbx+4Ch], 6
0x180031d71  jnz     short loc_180031D8D
0x180031d73  cmp     ebp, 1
0x180031d76  jnz     short loc_180031DB4
0x180031d78  mov     rdx, rsi; unsigned __int16 *
0x180031d7b  mov     rcx, rbx; this
0x180031d7e  call    ?AddSupportedVersion@ShimFactory@@AEAAJPEAG@Z; ShimFactory::AddSupportedVersion(ushort *)
0x180031d83  mov     r15d, eax
0x180031d86  xor     esi, esi
0x180031d88  jmp     loc_180031F75
0x180031d8d  cmp     dword ptr [rbx+4Ch], 5
0x180031d91  jnz     short loc_180031DB4
0x180031d93  cmp     ebp, 1
0x180031d96  jnz     short loc_180031DB4
0x180031d98  mov     rcx, [rbx+10h]; void *
0x180031d9c  test    rcx, rcx
0x180031d9f  jz      short loc_180031DA6
0x180031da1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031da6  mov     [rbx+10h], rsi
0x180031daa  xor     esi, esi
0x180031dac  mov     r15d, esi
0x180031daf  jmp     loc_180031F75
0x180031db4  cmp     ebp, 2
0x180031db7  jnz     short loc_180031DC4
0x180031db9  mov     [rbx+18h], rsi
0x180031dbd  xor     esi, esi
0x180031dbf  mov     r15d, esi
0x180031dc2  jmp     short loc_180031DC6
0x180031dc4  xor     esi, esi
0x180031dc6  cmp     dword ptr [rbx+38h], 1
0x180031dca  jnz     loc_180031F7B
0x180031dd0  cmp     [rbx+4Ch], r9d
0x180031dd4  jnz     loc_180031F7B
0x180031dda  cmp     ebp, 0Ah
0x180031ddd  jnz     loc_180031F7B
0x180031de3  mov     r8d, edi; unsigned int
0x180031de6  mov     rdx, r14; unsigned __int16 *
0x180031de9  mov     rcx, rbx; this
0x180031dec  call    ?CopyBuildFlavor@ShimFactory@@AEAAJPEBGK@Z; ShimFactory::CopyBuildFlavor(ushort const *,ulong)
0x180031df1  mov     r15d, eax
0x180031df4  jmp     loc_180031F75
0x180031df9  cmp     dword ptr [rbx+34h], 1
0x180031dfd  jnz     short loc_180031E59
0x180031dff  mov     esi, [rbx+4Ch]
0x180031e02  lea     eax, [rsi-5]
0x180031e05  cmp     eax, 1
0x180031e08  ja      short loc_180031E2D
0x180031e0a  mov     r9d, 7; unsigned int
0x180031e10  lea     r8, aVersion; "version"
0x180031e17  mov     edx, edi; unsigned int
0x180031e19  mov     rcx, r14; unsigned __int16 *
0x180031e1c  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031e21  test    eax, eax
0x180031e23  jnz     short loc_180031E2D
0x180031e25  lea     ebp, [rax+1]
0x180031e28  jmp     loc_180031D86
0x180031e2d  xor     ebp, ebp
0x180031e2f  cmp     esi, 5
0x180031e32  jnz     short loc_180031E57
0x180031e34  lea     r9d, [rbp+0Ch]; unsigned int
0x180031e38  mov     edx, edi; unsigned int
0x180031e3a  lea     r8, aImageversion; "imageVersion"
0x180031e41  mov     rcx, r14; unsigned __int16 *
0x180031e44  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031e49  xor     esi, esi
0x180031e4b  test    eax, eax
0x180031e4d  jnz     short loc_180031E59
0x180031e4f  lea     ebp, [rsi+2]
0x180031e52  jmp     loc_180031F75
0x180031e57  xor     esi, esi
0x180031e59  cmp     dword ptr [rbx+38h], 1
0x180031e5d  mov     r9d, 9
0x180031e63  jnz     loc_180031F7B
0x180031e69  mov     ebp, esi
0x180031e6b  cmp     [rbx+4Ch], r9d
0x180031e6f  jnz     loc_180031F7B
0x180031e75  mov     r9d, 7; unsigned int
0x180031e7b  lea     r8, aEnabled; "enabled"
0x180031e82  mov     edx, edi; unsigned int
0x180031e84  mov     rcx, r14; unsigned __int16 *
0x180031e87  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031e8c  mov     r9d, 9
0x180031e92  test    eax, eax
0x180031e94  jnz     loc_180031F7B
0x180031e9a  lea     ebp, [rax+0Ah]
0x180031e9d  jmp     loc_180031F7B
0x180031ea2  cmp     dword ptr [rbx+34h], 1
0x180031ea6  mov     [rbx+4Ch], esi
0x180031ea9  jnz     short loc_180031EF6
0x180031eab  mov     r9d, 0Fh; unsigned int
0x180031eb1  lea     r8, aRequiredruntim; "requiredRuntime"
0x180031eb8  mov     edx, edi; unsigned int
0x180031eba  mov     rcx, r14; unsigned __int16 *
0x180031ebd  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031ec2  test    eax, eax
0x180031ec4  jnz     short loc_180031ED2
0x180031ec6  mov     dword ptr [rbx+4Ch], 5
0x180031ecd  jmp     loc_180031F75
0x180031ed2  mov     r9d, 10h; unsigned int
0x180031ed8  lea     r8, aSupportedrunti; "supportedRuntime"
0x180031edf  mov     edx, edi; unsigned int
0x180031ee1  mov     rcx, r14; unsigned __int16 *
0x180031ee4  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031ee9  test    eax, eax
0x180031eeb  jnz     short loc_180031EF6
0x180031eed  mov     dword ptr [rbx+4Ch], 6
0x180031ef4  jmp     short loc_180031F75
0x180031ef6  cmp     dword ptr [rbx+38h], 1
0x180031efa  jnz     short loc_180031F21
0x180031efc  mov     r9d, 8; unsigned int
0x180031f02  lea     r8, aGcserver; "gcServer"
0x180031f09  mov     edx, edi; unsigned int
0x180031f0b  mov     rcx, r14; unsigned __int16 *
0x180031f0e  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031f13  test    eax, eax
0x180031f15  jnz     short loc_180031F21
0x180031f17  lea     r9d, [rax+9]
0x180031f1b  mov     [rbx+4Ch], r9d
0x180031f1f  jmp     short loc_180031F7B
0x180031f21  mov     r9d, 7; unsigned int
0x180031f27  lea     r8, aStartup; "startup"
0x180031f2e  mov     edx, edi; unsigned int
0x180031f30  mov     rcx, r14; unsigned __int16 *
0x180031f33  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031f38  test    eax, eax
0x180031f3a  jnz     short loc_180031F4C
0x180031f3c  mov     dword ptr [rbx+34h], 1
0x180031f43  mov     dword ptr [rbx+4Ch], 7
0x180031f4a  jmp     short loc_180031F75
0x180031f4c  mov     r9d, 7; unsigned int
0x180031f52  lea     r8, aRuntime; "runtime"
0x180031f59  mov     edx, edi; unsigned int
0x180031f5b  mov     rcx, r14; unsigned __int16 *
0x180031f5e  call    ?XMLStringCompare@@YAHPEBGK0K@Z; XMLStringCompare(ushort const *,ulong,ushort const *,ulong)
0x180031f63  test    eax, eax
0x180031f65  jnz     short loc_180031F75
0x180031f67  mov     dword ptr [rbx+38h], 1
0x180031f6e  mov     dword ptr [rbx+4Ch], 8
0x180031f75  mov     r9d, 9
0x180031f7b  mov     r10d, dword ptr [rsp+78h+arg_20]
0x180031f83  inc     r12d
0x180031f86  mov     [rsp+78h+arg_18], r12d
0x180031f8e  mov     eax, r12d
0x180031f91  jmp     loc_180031C8C
0x180031f96  mov     eax, r15d
0x180031f99  add     rsp, 38h
0x180031f9d  pop     r15
0x180031f9f  pop     r14
0x180031fa1  pop     r13
0x180031fa3  pop     r12
0x180031fa5  pop     rdi
0x180031fa6  pop     rsi
0x180031fa7  pop     rbp
0x180031fa8  pop     rbx
0x180031fa9  retn
```
