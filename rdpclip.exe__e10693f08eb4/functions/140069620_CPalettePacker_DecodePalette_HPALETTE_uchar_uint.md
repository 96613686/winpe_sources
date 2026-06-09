# CPalettePacker::DecodePalette(HPALETTE__ * *,uchar *,uint)

- ea: `0x140069620`
- end: `0x140069849`
- name: `?DecodePalette@CPalettePacker@@QEAAJPEAPEAUHPALETTE__@@PEAEI@Z`
- size: `553`
- prototype: `int(CPalettePacker *__hidden this, HPALETTE *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400614c8`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140011054`
- `0x1400186e4`
- `0x140069620`
- `0x140069a94`
- `0x14006a0e2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400697b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400697b7`
- `GDI32!CreatePalette` at `0x1400697a9`
- `GDI32!CreatePalette` at `0x1400697a9`
- `GDI32!DeleteObject` at `0x14006982f`
- `GDI32!DeleteObject` at `0x14006982f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400697d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400697d3`

## pseudocode

```c
__int64 __fastcall CPalettePacker::DecodePalette(
        CPalettePacker *this,
        HPALETTE *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  LOGPALETTE *v15; // rax
  LOGPALETTE *v16; // rsi
  unsigned int v17; // eax
  HPALETTE Palette; // rax
  signed int LastError; // eax

  *a2 = 0;
  if ( a4 < 4 )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 15;
LABEL_33:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids,
        CurrentThreadActivityIdPrefix);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v9 = a4 >> 2;
  v10 = 4LL * ((a4 >> 2) - 1);
  if ( v10 > 0xFFFFFFFF )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 16;
      goto LABEL_33;
    }
LABEL_34:
    if ( *a2 )
    {
      DeleteObject(*a2);
      *a2 = 0;
    }
    return v6;
  }
  v11 = v10 + 8;
  if ( v10 + 8 < v10 || v11 < 8 )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 17;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddi(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v12, v9, v11);
  }
  v15 = (LOGPALETTE *)PAL_System_MemAlloc(v11);
  v16 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids,
        v17,
        (__int64)"LOGPALETTE");
    }
    v6 = -2147024882;
    goto LABEL_34;
  }
  v15->palVersion = 768;
  v15->palNumEntries = v9;
  memcpy_0(v15->palPalEntry, a3, 4LL * v9);
  Palette = CreatePalette(v16);
  *a2 = Palette;
  if ( Palette )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  LocalFree(v16);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_34;
  return v6;
}

```

## disassembly

```asm
0x140069620  push    rbx
0x140069622  push    rbp
0x140069623  push    rsi
0x140069624  push    rdi
0x140069625  push    r14
0x140069627  sub     rsp, 30h
0x14006962b  mov     qword ptr [rdx], 0
0x140069632  mov     ebx, r9d
0x140069635  mov     rbp, r8
0x140069638  mov     r14, rdx
0x14006963b  cmp     r9d, 4
0x14006963f  jnb     short loc_140069680
0x140069641  mov     ebx, 834503E9h
0x140069646  mov     rax, cs:WPP_GLOBAL_Control
0x14006964d  lea     rdi, WPP_GLOBAL_Control
0x140069654  cmp     rax, rdi
0x140069657  jz      loc_140069827
0x14006965d  test    byte ptr [rax+1Ch], 1
0x140069661  jz      loc_140069827
0x140069667  cmp     byte ptr [rax+19h], 2
0x14006966b  jb      loc_140069827
0x140069671  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140069676  mov     edx, 0Fh
0x14006967b  jmp     loc_14006980D
0x140069680  shr     ebx, 2
0x140069683  mov     eax, 0FFFFFFFFh
0x140069688  lea     ecx, [rbx-1]
0x14006968b  shl     rcx, 2
0x14006968f  cmp     rcx, rax
0x140069692  jbe     short loc_1400696D3
0x140069694  mov     ebx, 834503E9h
0x140069699  mov     rax, cs:WPP_GLOBAL_Control
0x1400696a0  lea     rdi, WPP_GLOBAL_Control
0x1400696a7  cmp     rax, rdi
0x1400696aa  jz      loc_140069827
0x1400696b0  test    byte ptr [rax+1Ch], 1
0x1400696b4  jz      loc_140069827
0x1400696ba  cmp     byte ptr [rax+19h], 2
0x1400696be  jb      loc_140069827
0x1400696c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400696c9  mov     edx, 10h
0x1400696ce  jmp     loc_14006980D
0x1400696d3  lea     rsi, [rcx+8]
0x1400696d7  cmp     rsi, rcx
0x1400696da  jb      loc_1400697DF
0x1400696e0  cmp     rsi, 8
0x1400696e4  jb      loc_1400697DF
0x1400696ea  mov     rax, cs:WPP_GLOBAL_Control
0x1400696f1  lea     rdi, WPP_GLOBAL_Control
0x1400696f8  cmp     rax, rdi
0x1400696fb  jz      short loc_14006972A
0x1400696fd  test    byte ptr [rax+1Ch], 1
0x140069701  jz      short loc_14006972A
0x140069703  cmp     byte ptr [rax+19h], 5
0x140069707  jb      short loc_14006972A
0x140069709  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006970e  mov     rcx, cs:WPP_GLOBAL_Control
0x140069715  mov     r9d, eax
0x140069718  mov     [rsp+58h+var_30], rsi
0x14006971d  mov     dword ptr [rsp+58h+var_38], ebx
0x140069721  mov     rcx, [rcx+10h]
0x140069725  call    WPP_SF_Ddi
0x14006972a  mov     rcx, rsi
0x14006972d  call    PAL_System_MemAlloc
0x140069732  mov     rsi, rax
0x140069735  test    rax, rax
0x140069738  jnz     short loc_14006978A
0x14006973a  mov     rax, cs:WPP_GLOBAL_Control
0x140069741  cmp     rax, rdi
0x140069744  jz      short loc_140069780
0x140069746  test    byte ptr [rax+1Ch], 8
0x14006974a  jz      short loc_140069780
0x14006974c  cmp     byte ptr [rax+19h], 2
0x140069750  jb      short loc_140069780
0x140069752  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140069757  lea     rcx, aLogpalette; "LOGPALETTE"
0x14006975e  mov     r9d, eax
0x140069761  mov     [rsp+58h+var_38], rcx
0x140069766  lea     edx, [rsi+13h]
0x140069769  mov     rcx, cs:WPP_GLOBAL_Control
0x140069770  lea     r8, WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids
0x140069777  mov     rcx, [rcx+10h]
0x14006977b  call    WPP_SF_Ds
0x140069780  mov     ebx, 8007000Eh
0x140069785  jmp     loc_140069827
0x14006978a  mov     r8d, ebx
0x14006978d  lea     rcx, [rax+4]; void *
0x140069791  shl     r8, 2; Size
0x140069795  mov     rdx, rbp; Src
0x140069798  mov     word ptr [rax], 300h
0x14006979d  mov     [rax+2], bx
0x1400697a1  call    memcpy_0
0x1400697a6  mov     rcx, rsi; plpal
0x1400697a9  call    cs:__imp_CreatePalette
0x1400697af  mov     [r14], rax
0x1400697b2  test    rax, rax
0x1400697b5  jnz     short loc_1400697CE
0x1400697b7  call    cs:__imp_GetLastError
0x1400697bd  mov     ebx, eax
0x1400697bf  test    eax, eax
0x1400697c1  jle     short loc_1400697D0
0x1400697c3  movzx   ebx, ax
0x1400697c6  or      ebx, 80070000h
0x1400697cc  jmp     short loc_1400697D0
0x1400697ce  xor     ebx, ebx
0x1400697d0  mov     rcx, rsi; hMem
0x1400697d3  call    cs:__imp_LocalFree
0x1400697d9  test    ebx, ebx
0x1400697db  jns     short loc_14006983C
0x1400697dd  jmp     short loc_140069827
0x1400697df  mov     ebx, 834503E9h
0x1400697e4  mov     rax, cs:WPP_GLOBAL_Control
0x1400697eb  lea     rdi, WPP_GLOBAL_Control
0x1400697f2  cmp     rax, rdi
0x1400697f5  jz      short loc_140069827
0x1400697f7  test    byte ptr [rax+1Ch], 1
0x1400697fb  jz      short loc_140069827
0x1400697fd  cmp     byte ptr [rax+19h], 2
0x140069801  jb      short loc_140069827
0x140069803  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140069808  mov     edx, 11h
0x14006980d  mov     rcx, cs:WPP_GLOBAL_Control
0x140069814  lea     r8, WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids
0x14006981b  mov     r9d, eax
0x14006981e  mov     rcx, [rcx+10h]
0x140069822  call    WPP_SF_d
0x140069827  mov     rcx, [r14]; ho
0x14006982a  test    rcx, rcx
0x14006982d  jz      short loc_14006983C
0x14006982f  call    cs:__imp_DeleteObject
0x140069835  mov     qword ptr [r14], 0
0x14006983c  mov     eax, ebx
0x14006983e  add     rsp, 30h
0x140069842  pop     r14
0x140069844  pop     rdi
0x140069845  pop     rsi
0x140069846  pop     rbp
0x140069847  pop     rbx
0x140069848  retn
```
