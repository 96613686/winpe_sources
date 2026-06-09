# RtlCheckTokenCapability

- ea: `0x180012eb0`
- end: `0x180013309`
- name: `RtlCheckTokenCapability`
- size: `1113`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180013820`

## callees

- `0x180012e60`
- `0x180012eb0`
- `0x180015af0`
- `0x180015b30`
- `0x18015e2d0`
- `0x18015e4b0`
- `0x18015e6f0`
- `0x18015e8b0`
- `0x18015e8d0`
- `0x18015eb10`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlCheckTokenCapability(void *a1, unsigned __int8 *a2, _BYTE *a3)
{
  __int64 v6; // r8
  char v7; // di
  HANDLE v8; // rcx
  unsigned __int8 *v9; // rbx
  char v10; // si
  _BYTE *v11; // rdx
  unsigned int i; // r8d
  _BYTE *v13; // rcx
  __int64 v14; // r8
  _BYTE *v15; // rcx
  unsigned int j; // r8d
  __int64 v17; // r9
  int v18; // ebx
  HANDLE v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h]
  __int64 *v28; // [rsp+80h] [rbp-80h]
  _BYTE v29[48]; // [rsp+88h] [rbp-78h] BYREF
  void *Src[12]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+120h] [rbp+20h] BYREF
  int v32; // [rsp+128h] [rbp+28h]
  __int64 v33; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v34[152]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v35[56]; // [rsp+1D0h] [rbp+D0h] BYREF

  v24 = 0;
  v23 = 0;
  memset_thunk_772440563353939046(&v33, 0, 0xA0u);
  v20 = 0;
  v22 = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  memset(v29, 0, 44);
  v26 = 0;
  v27 = 0;
  memset_thunk_772440563353939046(Src, 0, 0x58u);
  v21 = 0;
  Handle = 0;
  *a3 = 0;
  if ( !(unsigned __int8)RtlIsCapabilitySid(a2) )
  {
    v18 = -1073741811;
    goto LABEL_40;
  }
  v7 = 2;
  if ( a1 )
  {
    v8 = a1;
    v20 = a1;
    goto LABEL_4;
  }
  LOBYTE(v6) = 1;
  v18 = NtOpenThreadTokenEx(-2, 8, v6, 0, &v20);
  if ( v18 == -1073741700 )
  {
    v18 = NtOpenProcessTokenEx(-1, 10, 0, &Handle);
    if ( v18 < 0 )
      goto LABEL_48;
    *(_QWORD *)&v29[40] = &v31;
    *(_DWORD *)v29 = 48;
    memset(&v29[8], 0, 20);
    *(_QWORD *)&v29[32] = 0;
    v31 = 0x20000000CLL;
    LOWORD(v32) = 1;
    v18 = NtDuplicateToken(Handle, 8, v29, 0, 2, &v20);
    NtClose(Handle);
  }
  if ( v18 >= 0 )
  {
    v8 = v20;
LABEL_4:
    v21 = 88;
    NtQueryInformationToken(v8, 1, Src, 88, &v21);
    v9 = (unsigned __int8 *)Src[0];
    v28 = 0;
    v26 = 1u;
    v27 = 0;
    if ( Src[0] )
    {
      *((void **)&v26 + 1) = Src[0];
      *(void **)&v27 = Src[0];
    }
    else
    {
      *(_QWORD *)&v27 = 0;
    }
    WORD1(v26) = 0;
    v33 = 10485762;
    if ( (unsigned __int8)RtlValidSid(Src[0]) && (unsigned __int8)v33 <= 4u )
    {
      v10 = 2;
      if ( (unsigned __int8)v33 > 2u )
        v10 = v33;
      if ( RtlValidAcl((__int64)&v33) )
      {
        v11 = v34;
        for ( i = 0; ; ++i )
        {
          v13 = &v34[WORD1(v33) - 8];
          if ( i >= WORD2(v33) )
            break;
          if ( v11 >= v13 )
            goto LABEL_19;
          v11 += *((unsigned __int16 *)v11 + 1);
        }
        if ( v11 <= v13 )
        {
          if ( v11 )
          {
            v14 = (unsigned __int16)(4 * (v9[1] + 4));
            if ( &v11[v14] <= v13 )
            {
              *((_WORD *)v11 + 1) = v14;
              *(_WORD *)v11 = 0;
              *((_DWORD *)v11 + 1) = 65537;
              memmove(v11 + 8, v9, 4LL * v9[1] + 8);
              ++WORD2(v33);
              LOBYTE(v33) = v10;
            }
          }
        }
      }
    }
LABEL_19:
    if ( (unsigned __int8)RtlValidSid(a2) && (unsigned __int8)v33 <= 4u )
    {
      if ( (unsigned __int8)v33 > 2u )
        v7 = v33;
      if ( RtlValidAcl((__int64)&v33) )
      {
        v15 = v34;
        for ( j = 0; j < WORD2(v33); ++j )
        {
          if ( v15 >= &v34[WORD1(v33) - 8] )
            goto LABEL_32;
          v15 += *((unsigned __int16 *)v15 + 1);
        }
        if ( v15 <= &v34[WORD1(v33) - 8] )
        {
          if ( v15 )
          {
            v17 = (unsigned __int16)(4 * (a2[1] + 4));
            if ( &v15[v17] <= &v34[WORD1(v33) - 8] )
            {
              *(_WORD *)v15 = 0;
              *((_WORD *)v15 + 1) = v17;
              *((_DWORD *)v15 + 1) = 65537;
              memmove(v15 + 8, a2, 4LL * a2[1] + 8);
              ++WORD2(v33);
              LOBYTE(v33) = v7;
            }
          }
        }
      }
    }
LABEL_32:
    if ( (_BYTE)v26 == 1 && (SWORD1(v26) & 0x8000u) == 0 )
    {
      v28 = &v33;
      WORD1(v26) = WORD1(v26) & 0xFFF3 | 4;
    }
    v22 = 56;
    v18 = ZwAccessCheck(&v26, v20, 65537, RtlpCheckTokenCapabilityGenericMapping, v35, &v22, &v24, &v23);
    if ( v18 >= 0 )
    {
      if ( !v23 && v24 == 65537 )
        *a3 = 1;
      v18 = 0;
    }
LABEL_40:
    if ( a1 )
      return (unsigned int)v18;
  }
LABEL_48:
  if ( v20 )
    NtClose(v20);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180012eb0  mov     [rsp-8+arg_18], rbx
0x180012eb5  push    rbp
0x180012eb6  push    rsi
0x180012eb7  push    rdi
0x180012eb8  push    r12
0x180012eba  push    r13
0x180012ebc  push    r14
0x180012ebe  push    r15
0x180012ec0  lea     rbp, [rsp-110h]
0x180012ec8  sub     rsp, 210h
0x180012ecf  mov     rax, cs:__security_cookie
0x180012ed6  xor     rax, rsp
0x180012ed9  mov     [rbp+140h+var_38], rax
0x180012ee0  mov     r12, r8
0x180012ee3  mov     r14, rdx
0x180012ee6  mov     r15, rcx
0x180012ee9  xor     r13d, r13d
0x180012eec  xor     edx, edx; Val
0x180012eee  mov     [rsp+240h+var_1EC], r13d
0x180012ef3  mov     r8d, 0A0h; Size
0x180012ef9  mov     [rsp+240h+var_1F0], r13d
0x180012efe  lea     rcx, [rbp+140h+var_110]; void *
0x180012f02  call    memset$thunk$772440563353939046
0x180012f07  xorps   xmm0, xmm0
0x180012f0a  mov     [rsp+240h+var_200], r13
0x180012f0f  xor     eax, eax
0x180012f11  mov     [rsp+240h+var_1F4], r13d
0x180012f16  movups  [rbp+140h+var_1A8], xmm0
0x180012f1a  xor     edx, edx; Val
0x180012f1c  mov     [rbp+140h+var_120], rax
0x180012f20  mov     r8d, 58h ; 'X'; Size
0x180012f26  mov     [rbp+140h+var_118], eax
0x180012f29  lea     rcx, [rbp+140h+Src]; void *
0x180012f2d  mov     [rbp+140h+var_1C0], rax
0x180012f31  movups  [rbp+140h+var_1A8+0Ch], xmm0
0x180012f35  movups  [rbp+140h+var_1B8], xmm0
0x180012f39  movups  [rsp+240h+var_1E0], xmm0
0x180012f3e  movups  [rsp+240h+var_1D0], xmm0
0x180012f43  call    memset$thunk$772440563353939046
0x180012f48  mov     rcx, r14
0x180012f4b  mov     [rsp+240h+var_1F8], r13d
0x180012f50  mov     [rsp+240h+Handle], r13
0x180012f55  mov     [r12], r13b
0x180012f59  call    RtlIsCapabilitySid
0x180012f5e  test    al, al
0x180012f60  jz      loc_1800132DD
0x180012f66  mov     edi, 2
0x180012f6b  test    r15, r15
0x180012f6e  jz      loc_180013227
0x180012f74  mov     rcx, r15
0x180012f77  mov     [rsp+240h+var_200], rcx
0x180012f7c  lea     rax, [rsp+240h+var_1F8]
0x180012f81  mov     [rsp+240h+var_1F8], 58h ; 'X'
0x180012f89  mov     r9d, 58h ; 'X'
0x180012f8f  mov     [rsp+240h+var_220], rax
0x180012f94  lea     r8, [rbp+140h+Src]
0x180012f98  mov     edx, 1
0x180012f9d  call    NtQueryInformationToken
0x180012fa2  mov     rbx, [rbp+140h+Src]
0x180012fa6  xorps   xmm0, xmm0
0x180012fa9  xor     eax, eax
0x180012fab  mov     [rbp+140h+var_1C0], rax
0x180012faf  movups  [rsp+240h+var_1E0], xmm0
0x180012fb4  mov     byte ptr [rsp+240h+var_1E0], 1
0x180012fb9  mov     qword ptr [rsp+240h+var_1E0+8], r13
0x180012fbe  movups  [rsp+240h+var_1D0], xmm0
0x180012fc3  test    rbx, rbx
0x180012fc6  jz      loc_1800132FF
0x180012fcc  mov     qword ptr [rsp+240h+var_1E0+8], rbx
0x180012fd1  mov     qword ptr [rsp+240h+var_1D0], rbx
0x180012fd6  mov     rcx, rbx
0x180012fd9  mov     word ptr [rsp+240h+var_1E0+2], r13w
0x180012fdf  mov     [rbp+140h+var_110], 0A00002h
0x180012fe7  call    RtlValidSid
0x180012fec  test    al, al
0x180012fee  jz      loc_18001309C
0x180012ff4  movzx   ecx, byte ptr [rbp+140h+var_110]
0x180012ff8  cmp     cl, 4
0x180012ffb  ja      loc_18001309C
0x180013001  cmp     cl, dil
0x180013004  mov     esi, edi
0x180013006  cmova   esi, ecx
0x180013009  lea     rcx, [rbp+140h+var_110]
0x18001300d  call    RtlValidAcl
0x180013012  test    al, al
0x180013014  jz      loc_18001309C
0x18001301a  movzx   r9d, word ptr [rbp+140h+var_110+4]
0x18001301f  lea     rdx, [rbp+140h+var_108]
0x180013023  movzx   r10d, word ptr [rbp+140h+var_110+2]
0x180013028  mov     r8d, r13d
0x18001302b  lea     rcx, [rbp+140h+var_110]
0x18001302f  add     rcx, r10
0x180013032  cmp     r8d, r9d
0x180013035  jnb     short loc_180013048
0x180013037  cmp     rdx, rcx
0x18001303a  jnb     short loc_18001309C
0x18001303c  movzx   eax, word ptr [rdx+2]
0x180013040  inc     r8d
0x180013043  add     rdx, rax
0x180013046  jmp     short loc_18001302B
0x180013048  cmp     rdx, rcx
0x18001304b  ja      short loc_18001309C
0x18001304d  test    rdx, rdx
0x180013050  jz      short loc_18001309C
0x180013052  movzx   eax, byte ptr [rbx+1]
0x180013056  add     ax, 4
0x18001305a  shl     ax, 2
0x18001305e  movzx   r8d, ax
0x180013062  lea     rax, [rdx+r8]
0x180013066  cmp     rax, rcx
0x180013069  ja      short loc_18001309C
0x18001306b  mov     [rdx+2], r8w
0x180013070  lea     rcx, [rdx+8]; void *
0x180013074  mov     [rdx], r13w
0x180013078  mov     dword ptr [rdx+4], 10001h
0x18001307f  mov     rdx, rbx; Src
0x180013082  movzx   r8d, byte ptr [rbx+1]
0x180013087  lea     r8, ds:8[r8*4]; Size
0x18001308f  call    memmove
0x180013094  inc     word ptr [rbp+140h+var_110+4]
0x180013098  mov     byte ptr [rbp+140h+var_110], sil
0x18001309c  mov     rcx, r14
0x18001309f  call    RtlValidSid
0x1800130a4  test    al, al
0x1800130a6  jz      loc_18001315A
0x1800130ac  movzx   ecx, byte ptr [rbp+140h+var_110]
0x1800130b0  cmp     cl, 4
0x1800130b3  ja      loc_18001315A
0x1800130b9  cmp     cl, dil
0x1800130bc  cmova   edi, ecx
0x1800130bf  lea     rcx, [rbp+140h+var_110]
0x1800130c3  call    RtlValidAcl
0x1800130c8  test    al, al
0x1800130ca  jz      loc_18001315A
0x1800130d0  movzx   r9d, word ptr [rbp+140h+var_110+4]
0x1800130d5  lea     rcx, [rbp+140h+var_108]
0x1800130d9  movzx   r10d, word ptr [rbp+140h+var_110+2]
0x1800130de  mov     r8d, r13d
0x1800130e1  cmp     r8d, r9d
0x1800130e4  jnb     short loc_1800130FE
0x1800130e6  lea     rdx, [rbp+140h+var_110]
0x1800130ea  add     rdx, r10
0x1800130ed  cmp     rcx, rdx
0x1800130f0  jnb     short loc_18001315A
0x1800130f2  movzx   eax, word ptr [rcx+2]
0x1800130f6  inc     r8d
0x1800130f9  add     rcx, rax
0x1800130fc  jmp     short loc_1800130E1
0x1800130fe  lea     r8, [rbp+140h+var_110]
0x180013102  add     r8, r10
0x180013105  cmp     rcx, r8
0x180013108  ja      short loc_18001315A
0x18001310a  test    rcx, rcx
0x18001310d  jz      short loc_18001315A
0x18001310f  movzx   eax, byte ptr [r14+1]
0x180013114  add     ax, 4
0x180013118  shl     ax, 2
0x18001311c  movzx   r9d, ax
0x180013120  lea     rax, [rcx+r9]
0x180013124  cmp     rax, r8
0x180013127  ja      short loc_18001315A
0x180013129  mov     [rcx], r13w
0x18001312d  mov     rdx, r14; Src
0x180013130  mov     [rcx+2], r9w
0x180013135  mov     dword ptr [rcx+4], 10001h
0x18001313c  add     rcx, 8; void *
0x180013140  movzx   r8d, byte ptr [r14+1]
0x180013145  lea     r8, ds:8[r8*4]; Size
0x18001314d  call    memmove
0x180013152  inc     word ptr [rbp+140h+var_110+4]
0x180013156  mov     byte ptr [rbp+140h+var_110], dil
0x18001315a  cmp     byte ptr [rsp+240h+var_1E0], 1
0x18001315f  jnz     short loc_180013184
0x180013161  movzx   eax, word ptr [rsp+240h+var_1E0+2]
0x180013166  test    ax, ax
0x180013169  js      short loc_180013184
0x18001316b  lea     rcx, [rbp+140h+var_110]
0x18001316f  mov     [rbp+140h+var_1C0], rcx
0x180013173  mov     ecx, 0FFF7h
0x180013178  and     ax, cx
0x18001317b  or      ax, 4
0x18001317f  mov     word ptr [rsp+240h+var_1E0+2], ax
0x180013184  mov     rdx, [rsp+240h+var_200]
0x180013189  lea     rax, [rsp+240h+var_1F0]
0x18001318e  mov     [rsp+240h+var_208], rax
0x180013193  lea     r9, RtlpCheckTokenCapabilityGenericMapping
0x18001319a  lea     rax, [rsp+240h+var_1EC]
0x18001319f  mov     [rsp+240h+var_1F4], 38h ; '8'
0x1800131a7  mov     [rsp+240h+var_210], rax
0x1800131ac  lea     rcx, [rsp+240h+var_1E0]
0x1800131b1  lea     rax, [rsp+240h+var_1F4]
0x1800131b6  mov     r8d, 10001h
0x1800131bc  mov     [rsp+240h+var_218], rax
0x1800131c1  lea     rax, [rbp+140h+var_70]
0x1800131c8  mov     [rsp+240h+var_220], rax
0x1800131cd  call    ZwAccessCheck
0x1800131d2  mov     ebx, eax
0x1800131d4  test    eax, eax
0x1800131d6  js      short loc_1800131F1
0x1800131d8  cmp     [rsp+240h+var_1F0], r13d
0x1800131dd  jnz     short loc_1800131EE
0x1800131df  cmp     [rsp+240h+var_1EC], 10001h
0x1800131e7  jnz     short loc_1800131EE
0x1800131e9  mov     byte ptr [r12], 1
0x1800131ee  mov     ebx, r13d
0x1800131f1  test    r15, r15
0x1800131f4  jz      loc_1800132E7
0x1800131fa  mov     eax, ebx
0x1800131fc  mov     rcx, [rbp+140h+var_38]
0x180013203  xor     rcx, rsp; StackCookie
0x180013206  call    __security_check_cookie
0x18001320b  mov     rbx, [rsp+240h+arg_18]
0x180013213  add     rsp, 210h
0x18001321a  pop     r15
0x18001321c  pop     r14
0x18001321e  pop     r13
0x180013220  pop     r12
0x180013222  pop     rdi
0x180013223  pop     rsi
0x180013224  pop     rbp
0x180013225  retn
0x180013227  lea     rax, [rsp+240h+var_200]
0x18001322c  xor     r9d, r9d
0x18001322f  mov     r8b, 1
0x180013232  mov     [rsp+240h+var_220], rax
0x180013237  mov     edx, 8
0x18001323c  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180013243  call    NtOpenThreadTokenEx
0x180013248  mov     ebx, eax
0x18001324a  cmp     eax, 0C000007Ch
0x18001324f  jnz     short loc_1800132CF
0x180013251  lea     r9, [rsp+240h+Handle]
0x180013256  xor     r8d, r8d
0x180013259  mov     edx, 0Ah
0x18001325e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013265  call    NtOpenProcessTokenEx
0x18001326a  mov     ebx, eax
0x18001326c  test    eax, eax
0x18001326e  js      short loc_1800132E7
0x180013270  mov     rcx, [rsp+240h+Handle]
0x180013275  lea     rax, [rbp+140h+var_120]
0x180013279  mov     [rbp+140h+var_190], rax
0x18001327d  lea     r8, [rbp+140h+var_1B8]
0x180013281  lea     rax, [rsp+240h+var_200]
0x180013286  mov     dword ptr [rbp+140h+var_1B8], 30h ; '0'
0x18001328d  mov     [rsp+240h+var_218], rax
0x180013292  xor     r9d, r9d
0x180013295  mov     edx, 8
0x18001329a  mov     dword ptr [rsp+240h+var_220], edi
0x18001329e  mov     qword ptr [rbp+140h+var_1B8+8], r13
0x1800132a2  mov     dword ptr [rbp+140h+var_1A8+8], r13d
0x1800132a6  mov     qword ptr [rbp+140h+var_1A8], r13
0x1800132aa  mov     [rbp+140h+var_198], r13
0x1800132ae  mov     dword ptr [rbp+140h+var_120], 0Ch
0x1800132b5  mov     dword ptr [rbp+140h+var_120+4], edi
0x1800132b8  mov     word ptr [rbp+140h+var_118], 1
0x1800132be  call    NtDuplicateToken
0x1800132c3  mov     rcx, [rsp+240h+Handle]; Handle
0x1800132c8  mov     ebx, eax
0x1800132ca  call    NtClose
0x1800132cf  test    ebx, ebx
0x1800132d1  js      short loc_1800132E7
0x1800132d3  mov     rcx, [rsp+240h+var_200]
0x1800132d8  jmp     loc_180012F7C
0x1800132dd  mov     ebx, 0C000000Dh
0x1800132e2  jmp     loc_1800131F1
0x1800132e7  mov     rcx, [rsp+240h+var_200]; Handle
0x1800132ec  test    rcx, rcx
0x1800132ef  jz      loc_1800131FA
0x1800132f5  call    NtClose
0x1800132fa  jmp     loc_1800131FA
0x1800132ff  mov     qword ptr [rsp+240h+var_1D0], r13
0x180013304  jmp     loc_180012FD6
```
