# VideoDCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,int,int)

- ea: `0x18001fae0`
- end: `0x18001fbb2`
- name: `?VideoDCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1HH@Z`
- size: `210`
- prototype: `void *__fastcall(enum tagColorConvertStatus *, const struct tagBITMAPINFOHEADER *, const struct tagBITMAPINFOHEADER *, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000a6d0`
- `0x18000a6dc`
- `0x180010bec`
- `0x18001fae0`
- `0x180028b6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb8a`

## pseudocode

```c
_QWORD *__fastcall VideoDCCCreate(
        enum tagColorConvertStatus *a1,
        const struct tagBITMAPINFOHEADER *a2,
        const struct tagBITMAPINFOHEADER *a3,
        int a4,
        int a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rdx
  void *v13; // rcx

  v9 = operator new(0x3C58u);
  v10 = v9;
  if ( v9 )
  {
    v9[1908] = 0;
    *((_DWORD *)v9 + 3819) = -1;
    *((_DWORD *)v9 + 3818) = -1;
    Init((struct DIRECTCOLORCONVFRM *)v9);
    initDeCC(a1, a2, a3, (struct DIRECTCOLORCONVFRM *)v10, a4, a5);
    if ( !*(_DWORD *)a1 )
      return v10;
    if ( *v10 )
    {
      operator delete((void *)*v10, v11);
      *v10 = 0;
    }
    v13 = (void *)v10[1];
    if ( v13 )
    {
      operator delete(v13, v11);
      v10[1] = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)v10 + 384);
    operator delete(v10, 0x3C58u);
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
0x18001fae0  push    rbx
0x18001fae2  push    rbp
0x18001fae3  push    rsi
0x18001fae4  push    rdi
0x18001fae5  push    r14
0x18001fae7  sub     rsp, 30h
0x18001faeb  mov     rdi, rcx
0x18001faee  mov     esi, r9d
0x18001faf1  mov     ecx, 3C58h; Size
0x18001faf6  mov     rbp, r8
0x18001faf9  mov     r14, rdx
0x18001fafc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb01  mov     rbx, rax
0x18001fb04  test    rax, rax
0x18001fb07  jz      loc_18001FB9F
0x18001fb0d  mov     qword ptr [rax+3BA0h], 0
0x18001fb18  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x18001fb1b  or      eax, 0FFFFFFFFh
0x18001fb1e  mov     [rbx+3BACh], eax
0x18001fb24  mov     [rbx+3BA8h], eax
0x18001fb2a  call    ?Init@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; Init(DIRECTCOLORCONVFRM *)
0x18001fb2f  mov     ecx, [rsp+58h+arg_20]
0x18001fb36  mov     r9, rbx; struct DIRECTCOLORCONVFRM *
0x18001fb39  mov     [rsp+58h+var_30], ecx; int
0x18001fb3d  mov     r8, rbp; struct tagBITMAPINFOHEADER *
0x18001fb40  mov     rcx, rdi; enum tagColorConvertStatus *
0x18001fb43  mov     [rsp+58h+var_38], esi; int
0x18001fb47  mov     rdx, r14; struct tagBITMAPINFOHEADER *
0x18001fb4a  call    ?initDeCC@@YAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1PEAUDIRECTCOLORCONVFRM@@JH@Z; initDeCC(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,DIRECTCOLORCONVFRM *,long,int)
0x18001fb4f  cmp     dword ptr [rdi], 0
0x18001fb52  jnz     short loc_18001FB59
0x18001fb54  mov     rax, rbx
0x18001fb57  jmp     short loc_18001FBA7
0x18001fb59  mov     rcx, [rbx]; void *
0x18001fb5c  test    rcx, rcx
0x18001fb5f  jz      short loc_18001FB6D
0x18001fb61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb66  mov     qword ptr [rbx], 0
0x18001fb6d  mov     rcx, [rbx+8]; void *
0x18001fb71  test    rcx, rcx
0x18001fb74  jz      short loc_18001FB83
0x18001fb76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb7b  mov     qword ptr [rbx+8], 0
0x18001fb83  lea     rcx, [rbx+3C00h]; lpCriticalSection
0x18001fb8a  call    cs:__imp_DeleteCriticalSection
0x18001fb90  mov     edx, 3C58h; unsigned __int64
0x18001fb95  mov     rcx, rbx; void *
0x18001fb98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb9d  jmp     short loc_18001FBA5
0x18001fb9f  mov     dword ptr [rdi], 1
0x18001fba5  xor     eax, eax
0x18001fba7  add     rsp, 30h
0x18001fbab  pop     r14
0x18001fbad  pop     rdi
0x18001fbae  pop     rsi
0x18001fbaf  pop     rbp
0x18001fbb0  pop     rbx
0x18001fbb1  retn
```
