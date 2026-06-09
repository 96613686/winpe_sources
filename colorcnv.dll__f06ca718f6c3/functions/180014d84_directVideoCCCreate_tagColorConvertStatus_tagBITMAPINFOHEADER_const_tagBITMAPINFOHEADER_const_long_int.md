# directVideoCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,long,int)

- ea: `0x180014d84`
- end: `0x180014e48`
- name: `?directVideoCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1JH@Z`
- size: `196`
- prototype: `struct DIRECTCOLORCONVFRM *__fastcall(enum tagColorConvertStatus *, const struct tagBITMAPINFOHEADER *, const struct tagBITMAPINFOHEADER *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c8bc`
- `0x180014e50`

## callees

- `0x18000a6d0`
- `0x18000a6dc`
- `0x180010bec`
- `0x180014d84`
- `0x180019ea4`

## pseudocode

```c
struct DIRECTCOLORCONVFRM *__fastcall directVideoCCCreate(
        enum tagColorConvertStatus *a1,
        const struct tagBITMAPINFOHEADER *a2,
        const struct tagBITMAPINFOHEADER *a3,
        int a4)
{
  struct DIRECTCOLORCONVFRM *v8; // rax
  struct DIRECTCOLORCONVFRM *v9; // rbx
  unsigned __int64 v10; // rdx
  void *v12; // rcx
  int v13; // [rsp+28h] [rbp-30h]

  v8 = (struct DIRECTCOLORCONVFRM *)operator new(0x3C58u);
  v9 = v8;
  if ( v8 )
  {
    *((_QWORD *)v8 + 1908) = 0;
    *((_DWORD *)v8 + 3819) = -1;
    *((_DWORD *)v8 + 3818) = -1;
    Init(v8);
    initDirectCC(a1, a2, a3, v9, a4, v13);
    if ( !*(_DWORD *)a1 )
    {
      *((_DWORD *)v9 + 3821) = 0;
      return v9;
    }
    if ( *(_QWORD *)v9 )
    {
      operator delete(*(void **)v9, v10);
      *(_QWORD *)v9 = 0;
    }
    v12 = (void *)*((_QWORD *)v9 + 1);
    if ( v12 )
    {
      operator delete(v12, v10);
      *((_QWORD *)v9 + 1) = 0;
    }
    operator delete(v9, 0x3C58u);
  }
  else
  {
    *(_DWORD *)a1 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180014d84  push    rbx
0x180014d86  push    rbp
0x180014d87  push    rsi
0x180014d88  push    rdi
0x180014d89  push    r14
0x180014d8b  sub     rsp, 30h
0x180014d8f  mov     rdi, rcx
0x180014d92  mov     esi, r9d
0x180014d95  mov     ecx, 3C58h; Size
0x180014d9a  mov     rbp, r8
0x180014d9d  mov     r14, rdx
0x180014da0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014da5  mov     rbx, rax
0x180014da8  test    rax, rax
0x180014dab  jz      loc_180014E35
0x180014db1  mov     qword ptr [rax+3BA0h], 0
0x180014dbc  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180014dbf  or      eax, 0FFFFFFFFh
0x180014dc2  mov     [rbx+3BACh], eax
0x180014dc8  mov     [rbx+3BA8h], eax
0x180014dce  call    ?Init@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; Init(DIRECTCOLORCONVFRM *)
0x180014dd3  mov     r9, rbx; struct DIRECTCOLORCONVFRM *
0x180014dd6  mov     [rsp+58h+var_38], esi; int
0x180014dda  mov     r8, rbp; struct tagBITMAPINFOHEADER *
0x180014ddd  mov     rdx, r14; struct tagBITMAPINFOHEADER *
0x180014de0  mov     rcx, rdi; enum tagColorConvertStatus *
0x180014de3  call    ?initDirectCC@@YAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1PEAUDIRECTCOLORCONVFRM@@JH@Z; initDirectCC(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,DIRECTCOLORCONVFRM *,long,int)
0x180014de8  cmp     dword ptr [rdi], 0
0x180014deb  jnz     short loc_180014DFC
0x180014ded  mov     dword ptr [rbx+3BB4h], 0
0x180014df7  mov     rax, rbx
0x180014dfa  jmp     short loc_180014E3D
0x180014dfc  mov     rcx, [rbx]; void *
0x180014dff  test    rcx, rcx
0x180014e02  jz      short loc_180014E10
0x180014e04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014e09  mov     qword ptr [rbx], 0
0x180014e10  mov     rcx, [rbx+8]; void *
0x180014e14  test    rcx, rcx
0x180014e17  jz      short loc_180014E26
0x180014e19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014e1e  mov     qword ptr [rbx+8], 0
0x180014e26  mov     edx, 3C58h; unsigned __int64
0x180014e2b  mov     rcx, rbx; void *
0x180014e2e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014e33  jmp     short loc_180014E3B
0x180014e35  mov     dword ptr [rdi], 1
0x180014e3b  xor     eax, eax
0x180014e3d  add     rsp, 30h
0x180014e41  pop     r14
0x180014e43  pop     rdi
0x180014e44  pop     rsi
0x180014e45  pop     rbp
0x180014e46  pop     rbx
0x180014e47  retn
```
