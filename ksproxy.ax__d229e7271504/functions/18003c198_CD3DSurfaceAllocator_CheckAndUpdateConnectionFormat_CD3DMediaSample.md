# CD3DSurfaceAllocator::CheckAndUpdateConnectionFormat(CD3DMediaSample *)

- ea: `0x18003c198`
- end: `0x18003c514`
- name: `?CheckAndUpdateConnectionFormat@CD3DSurfaceAllocator@@QEAAJPEAVCD3DMediaSample@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(CD3DSurfaceAllocator *__hidden this, struct CD3DMediaSample *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18003bde0`

## callees

- `0x180002b58`
- `0x180009c4c`
- `0x18001f620`
- `0x18001ffb0`
- `0x180025860`
- `0x18003c198`
- `0x18003cba0`
- `0x180044844`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CD3DSurfaceAllocator::CheckAndUpdateConnectionFormat(
        CD3DSurfaceAllocator *this,
        struct CD3DMediaSample *a2)
{
  bool v4; // zf
  int SurfacePitch; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // esi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, struct IDirect3DSurface9 **); // rcx
  unsigned int v10; // edi
  __int64 v11; // rbx
  int (__fastcall ***v12)(_QWORD, GUID *, unsigned int *); // rcx
  unsigned int v14[2]; // [rsp+20h] [rbp-49h] BYREF
  struct IDirect3DSurface9 *v15; // [rsp+28h] [rbp-41h] BYREF
  struct _AMMediaType v16; // [rsp+30h] [rbp-39h] BYREF

  v14[0] = 0;
  v16.majortype.Data1 = 0;
  memset_0(&v16.majortype.Data2, 0, 0x54u);
  v4 = *((_DWORD *)this + 44) == 0;
  v15 = 0;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids);
    SurfacePitch = 0;
    goto LABEL_44;
  }
  SurfacePitch = (*(__int64 (__fastcall **)(_QWORD, struct _AMMediaType *))(**((_QWORD **)this + 24) + 56LL))(
                   *((_QWORD *)this + 24),
                   &v16);
  if ( SurfacePitch < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_44;
    v7 = 40;
    goto LABEL_43;
  }
  if ( !memcmp_0(&v16.formattype, &FORMAT_VideoInfo2, 0x10u) || !memcmp_0(&v16.formattype, &FORMAT_VideoInfo, 0x10u) )
  {
    if ( !memcmp_0(&v16.formattype, &FORMAT_VideoInfo, 0x10u) )
    {
      v8 = *((_DWORD *)v16.pbFormat + 13);
    }
    else
    {
      v8 = 0;
      if ( !memcmp_0(&v16.formattype, &FORMAT_VideoInfo2, 0x10u) )
        v8 = *((_DWORD *)v16.pbFormat + 19);
    }
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IDirect3DSurface9 **))*((_QWORD *)a2 + 15);
    if ( v9 )
    {
      SurfacePitch = (**v9)(v9, &IID_IDirect3DSurface9, &v15);
      if ( SurfacePitch >= 0 )
      {
        SurfacePitch = CD3DSurfaceAllocator::GetSurfacePitch(this, v15, v14);
        if ( SurfacePitch >= 0 )
        {
          v10 = v14[0];
          if ( v14[0] == v8 )
            goto LABEL_44;
          v11 = 0;
          if ( !memcmp_0(&v16.formattype, &FORMAT_VideoInfo, 0x10u) )
            *((_DWORD *)v16.pbFormat + 13) = v10;
          if ( !memcmp_0(&v16.formattype, &FORMAT_VideoInfo2, 0x10u) )
            *((_DWORD *)v16.pbFormat + 19) = v10;
          v12 = (int (__fastcall ***)(_QWORD, GUID *, unsigned int *))*((_QWORD *)this + 24);
          *(_QWORD *)v14 = 0;
          if ( (**v12)(v12, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, v14) >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 40LL))(*(_QWORD *)v14);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 16LL))(*(_QWORD *)v14);
          }
          SurfacePitch = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v11 + 88LL))(v11, &v16);
          if ( SurfacePitch >= 0 )
          {
            SurfacePitch = (*(__int64 (__fastcall **)(struct CD3DMediaSample *, struct _AMMediaType *))(*(_QWORD *)a2 + 112LL))(
                             a2,
                             &v16);
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
              goto LABEL_44;
            v7 = 45;
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
              goto LABEL_44;
            v7 = 44;
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
            goto LABEL_44;
          v7 = 43;
        }
        goto LABEL_43;
      }
    }
    else
    {
      SurfacePitch = -2147418113;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_44;
    v7 = 42;
LABEL_43:
    WPP_SF_d(v6[2], v7, WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids, (unsigned int)SurfacePitch);
    goto LABEL_44;
  }
  SurfacePitch = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids);
LABEL_44:
  FreeMediaType(&v16);
  if ( v15 )
    ((void (__fastcall *)(struct IDirect3DSurface9 *))v15->lpVtbl->Release)(v15);
  return (unsigned int)SurfacePitch;
}

```

## disassembly

```asm
0x18003c198  mov     [rsp-8+arg_10], rbx
0x18003c19d  mov     [rsp-8+arg_18], rsi
0x18003c1a2  push    rbp
0x18003c1a3  push    rdi
0x18003c1a4  push    r13
0x18003c1a6  push    r14
0x18003c1a8  push    r15
0x18003c1aa  lea     rbp, [rsp-37h]
0x18003c1af  sub     rsp, 0A0h
0x18003c1b6  mov     rax, cs:__security_cookie
0x18003c1bd  xor     rax, rsp
0x18003c1c0  mov     [rbp+57h+var_30], rax
0x18003c1c4  mov     r15, rdx
0x18003c1c7  mov     [rbp+57h+var_A0], 0
0x18003c1ce  xor     edx, edx; Val
0x18003c1d0  mov     [rbp+57h+var_90.majortype.Data1], 0
0x18003c1d7  mov     r14, rcx
0x18003c1da  lea     rcx, [rbp+57h+var_90.majortype.Data2]; void *
0x18003c1de  lea     r8d, [rdx+54h]; Size
0x18003c1e2  call    memset_0
0x18003c1e7  cmp     dword ptr [r14+0B0h], 0
0x18003c1ef  mov     [rbp+57h+var_98], 0
0x18003c1f7  jnz     short loc_18003C22E
0x18003c1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c200  lea     rax, WPP_GLOBAL_Control
0x18003c207  cmp     rcx, rax
0x18003c20a  jz      short loc_18003C227
0x18003c20c  cmp     byte ptr [rcx+19h], 3
0x18003c210  jb      short loc_18003C227
0x18003c212  mov     rcx, [rcx+10h]
0x18003c216  lea     r8, WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids
0x18003c21d  mov     edx, 27h ; '''
0x18003c222  call    WPP_SF_
0x18003c227  xor     ebx, ebx
0x18003c229  jmp     loc_18003C4CB
0x18003c22e  mov     rcx, [r14+0C0h]
0x18003c235  lea     rdx, [rbp+57h+var_90]
0x18003c239  mov     rax, [rcx]
0x18003c23c  mov     rax, [rax+38h]
0x18003c240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c245  mov     ebx, eax
0x18003c247  test    eax, eax
0x18003c249  jns     short loc_18003C276
0x18003c24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c252  lea     rax, WPP_GLOBAL_Control
0x18003c259  cmp     rcx, rax
0x18003c25c  jz      loc_18003C4CB
0x18003c262  cmp     byte ptr [rcx+19h], 3
0x18003c266  jb      loc_18003C4CB
0x18003c26c  mov     edx, 28h ; '('
0x18003c271  jmp     loc_18003C4B8
0x18003c276  mov     r13d, 10h
0x18003c27c  lea     rdx, FORMAT_VideoInfo2; Buf2
0x18003c283  mov     r8d, r13d; Size
0x18003c286  lea     rcx, [rbp+57h+var_90.formattype]; Buf1
0x18003c28a  call    memcmp_0
0x18003c28f  test    eax, eax
0x18003c291  jz      short loc_18003C2E5
0x18003c293  mov     r8d, r13d; Size
0x18003c296  lea     rdx, FORMAT_VideoInfo; Buf2
0x18003c29d  lea     rcx, [rbp+57h+var_90.formattype]; Buf1
0x18003c2a1  call    memcmp_0
0x18003c2a6  test    eax, eax
0x18003c2a8  jz      short loc_18003C2E5
0x18003c2aa  xor     ebx, ebx
0x18003c2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2b3  lea     rax, WPP_GLOBAL_Control
0x18003c2ba  cmp     rcx, rax
0x18003c2bd  jz      loc_18003C4CB
0x18003c2c3  cmp     byte ptr [rcx+19h], 3
0x18003c2c7  jb      loc_18003C4CB
0x18003c2cd  mov     rcx, [rcx+10h]
0x18003c2d1  lea     edx, [rbx+29h]
0x18003c2d4  lea     r8, WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids
0x18003c2db  call    WPP_SF_
0x18003c2e0  jmp     loc_18003C4CB
0x18003c2e5  mov     r8, r13; Size
0x18003c2e8  lea     rdx, FORMAT_VideoInfo; Buf2
0x18003c2ef  lea     rcx, [rbp+57h+var_90.formattype]; Buf1
0x18003c2f3  call    memcmp_0
0x18003c2f8  test    eax, eax
0x18003c2fa  jnz     short loc_18003C305
0x18003c2fc  mov     rax, [rbp+57h+var_90.pbFormat]
0x18003c300  mov     esi, [rax+34h]
0x18003c303  jmp     short loc_18003C325
0x18003c305  mov     r8, r13; Size
0x18003c308  lea     rdx, FORMAT_VideoInfo2; Buf2
0x18003c30f  lea     rcx, [rbp+57h+var_90.formattype]; Buf1
0x18003c313  xor     esi, esi
0x18003c315  call    memcmp_0
0x18003c31a  test    eax, eax
0x18003c31c  jnz     short loc_18003C325
0x18003c31e  mov     rax, [rbp+57h+var_90.pbFormat]
0x18003c322  mov     esi, [rax+4Ch]
0x18003c325  mov     rcx, [r15+78h]
0x18003c329  test    rcx, rcx
0x18003c32c  jz      loc_18003C495
0x18003c332  mov     rax, [rcx]
0x18003c335  lea     r8, [rbp+57h+var_98]
0x18003c339  lea     rdx, IID_IDirect3DSurface9
0x18003c340  mov     rax, [rax]
0x18003c343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c348  mov     ebx, eax
0x18003c34a  test    eax, eax
0x18003c34c  js      loc_18003C49A
0x18003c352  mov     rdx, [rbp+57h+var_98]; struct IDirect3DSurface9 *
0x18003c356  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x18003c35a  mov     rcx, r14; this
0x18003c35d  call    ?GetSurfacePitch@CD3DSurfaceAllocator@@QEAAJPEAUIDirect3DSurface9@@AEAK@Z; CD3DSurfaceAllocator::GetSurfacePitch(IDirect3DSurface9 *,ulong &)
0x18003c362  mov     ebx, eax
0x18003c364  test    eax, eax
0x18003c366  jns     short loc_18003C393
0x18003c368  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c36f  lea     rax, WPP_GLOBAL_Control
0x18003c376  cmp     rcx, rax
0x18003c379  jz      loc_18003C4CB
0x18003c37f  cmp     byte ptr [rcx+19h], 3
0x18003c383  jb      loc_18003C4CB
0x18003c389  mov     edx, 2Bh ; '+'
0x18003c38e  jmp     loc_18003C4B8
0x18003c393  mov     edi, [rbp+57h+var_A0]
0x18003c396  cmp     edi, esi
0x18003c398  jz      loc_18003C4CB
0x18003c39e  mov     r8, r13; Size
0x18003c3a1  lea     rdx, FORMAT_VideoInfo; Buf2
0x18003c3a8  lea     rcx, [rbp+57h+var_90.formattype]; Buf1
0x18003c3ac  xor     ebx, ebx
0x18003c3ae  call    memcmp_0
0x18003c3b3  test    eax, eax
0x18003c3b5  jnz     short loc_18003C3BE
0x18003c3b7  mov     rax, [rbp+57h+var_90.pbFormat]
0x18003c3bb  mov     [rax+34h], edi
0x18003c3be  mov     r8, r13; Size
0x18003c3c1  lea     rdx, FORMAT_VideoInfo2; Buf2
0x18003c3c8  lea     rcx, [rbp+57h+var_90.formattype]; Buf1
0x18003c3cc  call    memcmp_0
0x18003c3d1  test    eax, eax
0x18003c3d3  jnz     short loc_18003C3DC
0x18003c3d5  mov     rax, [rbp+57h+var_90.pbFormat]
0x18003c3d9  mov     [rax+4Ch], edi
0x18003c3dc  mov     rcx, [r14+0C0h]
0x18003c3e3  lea     r8, [rbp+57h+var_A0]
0x18003c3e7  mov     qword ptr [rbp+57h+var_A0], rbx
0x18003c3eb  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x18003c3f2  mov     rax, [rcx]
0x18003c3f5  mov     rax, [rax]
0x18003c3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3fd  test    eax, eax
0x18003c3ff  js      short loc_18003C427
0x18003c401  mov     rcx, qword ptr [rbp+57h+var_A0]
0x18003c405  mov     rax, [rcx]
0x18003c408  mov     rax, [rax+28h]
0x18003c40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c411  mov     rdx, qword ptr [rbp+57h+var_A0]
0x18003c415  mov     rbx, rax
0x18003c418  mov     rcx, [rdx]
0x18003c41b  mov     rax, [rcx+10h]
0x18003c41f  mov     rcx, rdx
0x18003c422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c427  mov     rcx, [rbx]
0x18003c42a  lea     rdx, [rbp+57h+var_90]
0x18003c42e  mov     rax, [rcx+58h]
0x18003c432  mov     rcx, rbx
0x18003c435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c43a  mov     ebx, eax
0x18003c43c  test    eax, eax
0x18003c43e  jns     short loc_18003C460
0x18003c440  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c447  lea     rax, WPP_GLOBAL_Control
0x18003c44e  cmp     rcx, rax
0x18003c451  jz      short loc_18003C4CB
0x18003c453  cmp     byte ptr [rcx+19h], 3
0x18003c457  jb      short loc_18003C4CB
0x18003c459  mov     edx, 2Ch ; ','
0x18003c45e  jmp     short loc_18003C4B8
0x18003c460  mov     rax, [r15]
0x18003c463  lea     rdx, [rbp+57h+var_90]
0x18003c467  mov     rcx, r15
0x18003c46a  mov     rax, [rax+70h]
0x18003c46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c473  mov     ebx, eax
0x18003c475  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c47c  lea     rax, WPP_GLOBAL_Control
0x18003c483  cmp     rcx, rax
0x18003c486  jz      short loc_18003C4CB
0x18003c488  cmp     byte ptr [rcx+19h], 3
0x18003c48c  jb      short loc_18003C4CB
0x18003c48e  mov     edx, 2Dh ; '-'
0x18003c493  jmp     short loc_18003C4B8
0x18003c495  mov     ebx, 8000FFFFh
0x18003c49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c4a1  lea     rax, WPP_GLOBAL_Control
0x18003c4a8  cmp     rcx, rax
0x18003c4ab  jz      short loc_18003C4CB
0x18003c4ad  cmp     byte ptr [rcx+19h], 3
0x18003c4b1  jb      short loc_18003C4CB
0x18003c4b3  mov     edx, 2Ah ; '*'
0x18003c4b8  mov     rcx, [rcx+10h]
0x18003c4bc  lea     r8, WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids
0x18003c4c3  mov     r9d, ebx
0x18003c4c6  call    WPP_SF_d
0x18003c4cb  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x18003c4cf  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18003c4d4  mov     rcx, [rbp+57h+var_98]
0x18003c4d8  test    rcx, rcx
0x18003c4db  jz      short loc_18003C4E9
0x18003c4dd  mov     rax, [rcx]
0x18003c4e0  mov     rax, [rax+10h]
0x18003c4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4e9  mov     eax, ebx
0x18003c4eb  mov     rcx, [rbp+57h+var_30]
0x18003c4ef  xor     rcx, rsp; StackCookie
0x18003c4f2  call    __security_check_cookie
0x18003c4f7  lea     r11, [rsp+0C0h+var_20]
0x18003c4ff  mov     rbx, [r11+40h]
0x18003c503  mov     rsi, [r11+48h]
0x18003c507  mov     rsp, r11
0x18003c50a  pop     r15
0x18003c50c  pop     r14
0x18003c50e  pop     r13
0x18003c510  pop     rdi
0x18003c511  pop     rbp
0x18003c512  retn
```
