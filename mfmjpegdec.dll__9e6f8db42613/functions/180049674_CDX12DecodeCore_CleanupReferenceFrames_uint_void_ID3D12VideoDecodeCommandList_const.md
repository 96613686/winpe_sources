# CDX12DecodeCore::CleanupReferenceFrames(uint,void *,ID3D12VideoDecodeCommandList * const)

- ea: `0x180049674`
- end: `0x180049798`
- name: `?CleanupReferenceFrames@CDX12DecodeCore@@IEAAJIPEAXQEAUID3D12VideoDecodeCommandList@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(CDX12DecodeCore *__hidden this, unsigned int, void *, struct ID3D12VideoDecodeCommandList *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a550`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x180049674`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall CDX12DecodeCore::CleanupReferenceFrames(
        CDX12DecodeCore *this,
        int a2,
        void *a3,
        struct ID3D12VideoDecodeCommandList *const a4)
{
  __int64 v8; // rax
  unsigned int v9; // r14d
  unsigned int v10; // r8d
  __int64 i; // rbx
  __int64 v12; // rdx
  __int64 v13; // rdi
  struct ID3D12VideoDecodeCommandListVtbl *lpVtbl; // rax
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[156]; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v21[37]; // [rsp+100h] [rbp+0h] BYREF

  v19 = 255;
  v17 = 0;
  v18 = 0;
  memset_0(v20, 0, 0x90u);
  v16 = 0;
  v8 = *(_QWORD *)this;
  memset(v21, 0, sizeof(v21));
  v9 = (*(__int64 (__fastcall **)(CDX12DecodeCore *, void *, int *, unsigned int *))(v8 + 168))(this, a3, &v19, &v16);
  if ( !v9 )
  {
    v10 = v16;
    for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
    {
      v12 = *(unsigned int *)&v20[4 * i - 4];
      if ( (_DWORD)v12 != a2 && (unsigned int)v12 < 0x25 )
      {
        v13 = (unsigned int)v12;
        if ( !v21[v12] )
        {
          if ( *((_QWORD *)this + v12 + 15) )
          {
            *((_QWORD *)&v17 + 1) = *((_QWORD *)this + v12 + 15);
            LODWORD(v18) = *((_DWORD *)this + v12 + 104);
            lpVtbl = a4->lpVtbl;
            *(_QWORD *)((char *)&v18 + 4) = 0x10000;
            ((void (__fastcall *)(struct ID3D12VideoDecodeCommandList *const, __int64, __int128 *))lpVtbl->ResourceBarrier)(
              a4,
              1,
              &v17);
            v10 = v16;
            v21[v13] = 1;
          }
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180049674  push    rbp
0x180049676  push    rbx
0x180049677  push    rsi
0x180049678  push    rdi
0x180049679  push    r12
0x18004967b  push    r14
0x18004967d  push    r15
0x18004967f  lea     rbp, [rsp-30h]
0x180049684  sub     rsp, 130h
0x18004968b  mov     rax, cs:__security_cookie
0x180049692  xor     rax, rsp
0x180049695  mov     [rbp+60h+var_38], rax
0x180049699  xorps   xmm0, xmm0
0x18004969c  mov     [rsp+160h+var_100], 0FFh
0x1800496a4  mov     rbx, r8
0x1800496a7  mov     r12d, edx
0x1800496aa  mov     rsi, rcx
0x1800496ad  xor     edx, edx; Val
0x1800496af  mov     r8d, 90h; Size
0x1800496b5  lea     rcx, [rsp+160h+var_FC]; void *
0x1800496ba  movups  [rsp+160h+var_128], xmm0
0x1800496bf  mov     r15, r9
0x1800496c2  movups  [rsp+160h+var_118], xmm0
0x1800496c7  call    memset_0
0x1800496cc  xor     eax, eax
0x1800496ce  lea     r9, [rsp+160h+var_130]
0x1800496d3  xorps   xmm0, xmm0
0x1800496d6  mov     [rsp+160h+var_130], eax
0x1800496da  movups  xmmword ptr [rbp+60h+var_50], xmm0
0x1800496de  mov     qword ptr [rbp+60h+var_50+0Dh], rax
0x1800496e2  lea     r8, [rsp+160h+var_100]
0x1800496e7  mov     rax, [rsi]
0x1800496ea  mov     rdx, rbx
0x1800496ed  mov     rcx, rsi
0x1800496f0  movups  [rbp+60h+var_60], xmm0
0x1800496f4  mov     rax, [rax+0A8h]
0x1800496fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049700  mov     r14d, eax
0x180049703  test    eax, eax
0x180049705  jnz     short loc_180049777
0x180049707  mov     r8d, [rsp+160h+var_130]
0x18004970c  xor     ebx, ebx
0x18004970e  test    r8d, r8d
0x180049711  jz      short loc_180049777
0x180049713  mov     edx, [rsp+rbx*4+160h+var_100]
0x180049717  cmp     edx, r12d
0x18004971a  jz      short loc_180049770
0x18004971c  cmp     edx, 25h ; '%'
0x18004971f  jnb     short loc_180049770
0x180049721  cmp     byte ptr [rbp+rdx+60h+var_60], 0
0x180049726  mov     edi, edx
0x180049728  jnz     short loc_180049770
0x18004972a  mov     rax, [rsi+rdx*8+78h]
0x18004972f  test    rax, rax
0x180049732  jz      short loc_180049770
0x180049734  mov     qword ptr [rsp+160h+var_128+8], rax
0x180049739  lea     r8, [rsp+160h+var_128]
0x18004973e  mov     eax, [rsi+rdx*4+1A0h]
0x180049745  mov     rcx, r15
0x180049748  mov     dword ptr [rsp+160h+var_118], eax
0x18004974c  mov     edx, 1
0x180049751  mov     rax, [r15]
0x180049754  mov     qword ptr [rsp+160h+var_118+4], 10000h
0x18004975d  mov     rax, [rax+60h]
0x180049761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049766  mov     r8d, [rsp+160h+var_130]
0x18004976b  mov     byte ptr [rbp+rdi+60h+var_60], 1
0x180049770  inc     ebx
0x180049772  cmp     ebx, r8d
0x180049775  jb      short loc_180049713
0x180049777  mov     eax, r14d
0x18004977a  mov     rcx, [rbp+60h+var_38]
0x18004977e  xor     rcx, rsp; StackCookie
0x180049781  call    __security_check_cookie
0x180049786  add     rsp, 130h
0x18004978d  pop     r15
0x18004978f  pop     r14
0x180049791  pop     r12
0x180049793  pop     rdi
0x180049794  pop     rsi
0x180049795  pop     rbx
0x180049796  pop     rbp
0x180049797  retn
```
