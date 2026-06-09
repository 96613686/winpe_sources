# PathBuffer::Initialize(ushort const *)

- ea: `0x180013660`
- end: `0x1800137d0`
- name: `?Initialize@PathBuffer@@QEAAJPEBG@Z`
- size: `368`
- prototype: `__int64 __fastcall(PathBuffer *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180012be8`
- `0x1800132c8`

## callees

- `0x180002028`
- `0x1800022d8`
- `0x1800037a0`
- `0x18000b978`
- `0x18000b9bc`
- `0x180013660`

## pseudocode

```c
__int64 __fastcall PathBuffer::Initialize(PathBuffer *this, const unsigned __int16 *a2)
{
  bool v2; // zf
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rsi
  unsigned int v13; // eax
  unsigned __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this == 0;
  v15 = 0;
  if ( v2 )
  {
    v8 = StringCchLengthW(a2, 0x104u, &v15);
    v5 = v8;
    if ( !v8 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v8);
    if ( v5 >= 0 )
    {
LABEL_11:
      v9 = v15 + 1;
      v10 = 2 * (v15 + 1);
      if ( !is_mul_ok(v15 + 1, 2u) )
        v10 = -1;
      v11 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      if ( v11 )
      {
        v13 = StringCchCopyW(v11, v9, a2);
        v5 = v13;
        if ( !v13 )
          goto LABEL_23;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v13);
        if ( v5 < 0 )
          operator delete(v12);
        else
LABEL_23:
          *(_QWORD *)this = v12;
      }
      else
      {
        v5 = -2147024882;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v7 = 12;
          goto LABEL_5;
        }
      }
    }
  }
  else
  {
    v5 = -2147023649;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v7 = 10;
LABEL_5:
      WPP_SF_d(v6[2], v7, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, (unsigned int)v5);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013660  mov     [rsp+arg_8], rbx
0x180013665  mov     [rsp+arg_10], rbp
0x18001366a  push    rsi
0x18001366b  push    rdi
0x18001366c  push    r14
0x18001366e  sub     rsp, 20h
0x180013672  cmp     qword ptr [rcx], 0
0x180013676  mov     rbp, rdx
0x180013679  mov     r14, rcx
0x18001367c  mov     [rsp+38h+arg_0], 0
0x180013685  jz      short loc_1800136CA
0x180013687  mov     ebx, 800704DFh
0x18001368c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013693  lea     rdi, WPP_GLOBAL_Control
0x18001369a  cmp     rcx, rdi
0x18001369d  jz      loc_1800137BB
0x1800136a3  test    byte ptr [rcx+1Ch], 40h
0x1800136a7  jz      loc_1800137BB
0x1800136ad  mov     edx, 0Ah
0x1800136b2  mov     rcx, [rcx+10h]
0x1800136b6  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x1800136bd  mov     r9d, ebx
0x1800136c0  call    WPP_SF_d
0x1800136c5  jmp     loc_1800137BB
0x1800136ca  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x1800136cf  mov     edx, 104h; unsigned __int64
0x1800136d4  mov     rcx, rbp; unsigned __int16 *
0x1800136d7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800136dc  lea     rdi, WPP_GLOBAL_Control
0x1800136e3  mov     ebx, eax
0x1800136e5  test    eax, eax
0x1800136e7  jz      short loc_18001371B
0x1800136e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136f0  cmp     rcx, rdi
0x1800136f3  jz      short loc_180013713
0x1800136f5  test    byte ptr [rcx+1Ch], 40h
0x1800136f9  jz      short loc_180013713
0x1800136fb  mov     rcx, [rcx+10h]
0x1800136ff  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013706  mov     edx, 0Bh
0x18001370b  mov     r9d, eax
0x18001370e  call    WPP_SF_d
0x180013713  test    ebx, ebx
0x180013715  js      loc_1800137BB
0x18001371b  mov     rbx, [rsp+38h+arg_0]
0x180013720  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013727  inc     rbx
0x18001372a  mov     eax, 2
0x18001372f  mul     rbx
0x180013732  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013739  cmovb   rax, rcx
0x18001373d  mov     rcx, rax; unsigned __int64
0x180013740  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013745  mov     rsi, rax
0x180013748  test    rax, rax
0x18001374b  jnz     short loc_18001376C
0x18001374d  mov     ebx, 8007000Eh
0x180013752  mov     rcx, cs:WPP_GLOBAL_Control
0x180013759  cmp     rcx, rdi
0x18001375c  jz      short loc_1800137BB
0x18001375e  test    byte ptr [rcx+1Ch], 40h
0x180013762  jz      short loc_1800137BB
0x180013764  lea     edx, [rax+0Ch]
0x180013767  jmp     loc_1800136B2
0x18001376c  mov     r8, rbp; unsigned __int16 *
0x18001376f  mov     rdx, rbx; unsigned __int64
0x180013772  mov     rcx, rsi; unsigned __int16 *
0x180013775  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001377a  mov     ebx, eax
0x18001377c  test    eax, eax
0x18001377e  jz      short loc_1800137B8
0x180013780  mov     rcx, cs:WPP_GLOBAL_Control
0x180013787  cmp     rcx, rdi
0x18001378a  jz      short loc_1800137AA
0x18001378c  test    byte ptr [rcx+1Ch], 40h
0x180013790  jz      short loc_1800137AA
0x180013792  mov     rcx, [rcx+10h]
0x180013796  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001379d  mov     edx, 0Dh
0x1800137a2  mov     r9d, eax
0x1800137a5  call    WPP_SF_d
0x1800137aa  test    ebx, ebx
0x1800137ac  jns     short loc_1800137B8
0x1800137ae  mov     rcx, rsi; Block
0x1800137b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800137b6  jmp     short loc_1800137BB
0x1800137b8  mov     [r14], rsi
0x1800137bb  mov     rbp, [rsp+38h+arg_10]
0x1800137c0  mov     eax, ebx
0x1800137c2  mov     rbx, [rsp+38h+arg_8]
0x1800137c7  add     rsp, 20h
0x1800137cb  pop     r14
0x1800137cd  pop     rdi
0x1800137ce  pop     rsi
0x1800137cf  retn
```
