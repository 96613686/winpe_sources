# GetNfsShareList(_LIST_ENTRY *)

- ea: `0x18001e418`
- end: `0x18001e8af`
- name: `?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z`
- size: `1175`
- prototype: `unsigned int __fastcall(struct _LIST_ENTRY *)`
- caller_count: `11`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180009c88`
- `0x18000a9d4`
- `0x18000ab68`
- `0x180019010`
- `0x18001d024`
- `0x18001d798`
- `0x18001dfb4`
- `0x18001e0a4`
- `0x18001eca0`
- `0x180020920`
- `0x180020b64`

## callees

- `0x180006a54`
- `0x180009670`
- `0x18001e2d4`
- `0x18001e358`
- `0x18001e418`
- `0x18001eb14`
- `0x1800203d8`
- `0x180020720`
- `0x1800219fc`
- `0x180029c30`
- `0x18002c874`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e68b`
- `msvcrt!_wcsicmp` at `0x18001e68b`
- `msvcrt!free` at `0x18001e7cd`
- `msvcrt!free` at `0x18001e7cd`
- `KERNEL32!HeapFree` at `0x18001e53c`
- `KERNEL32!HeapFree` at `0x18001e7ab`
- `KERNEL32!HeapFree` at `0x18001e871`
- `KERNEL32!HeapFree` at `0x18001e53c`
- `KERNEL32!HeapFree` at `0x18001e7ab`
- `KERNEL32!HeapFree` at `0x18001e871`
- `KERNEL32!GetLastError` at `0x18001e4b9`
- `KERNEL32!GetLastError` at `0x18001e4b9`
- `KERNEL32!HeapAlloc` at `0x18001e4e1`
- `KERNEL32!HeapAlloc` at `0x18001e58a`
- `KERNEL32!HeapAlloc` at `0x18001e4e1`
- `KERNEL32!HeapAlloc` at `0x18001e58a`
- `KERNEL32!GetProcessHeap` at `0x18001e4c9`
- `KERNEL32!GetProcessHeap` at `0x18001e52e`
- `KERNEL32!GetProcessHeap` at `0x18001e542`
- `KERNEL32!GetProcessHeap` at `0x18001e579`
- `KERNEL32!GetProcessHeap` at `0x18001e79c`
- `KERNEL32!GetProcessHeap` at `0x18001e863`
- `KERNEL32!GetProcessHeap` at `0x18001e4c9`
- `KERNEL32!GetProcessHeap` at `0x18001e52e`
- `KERNEL32!GetProcessHeap` at `0x18001e542`
- `KERNEL32!GetProcessHeap` at `0x18001e579`
- `KERNEL32!GetProcessHeap` at `0x18001e79c`
- `KERNEL32!GetProcessHeap` at `0x18001e863`
- `KERNEL32!GetComputerNameExW` at `0x18001e4af`
- `KERNEL32!GetComputerNameExW` at `0x18001e4af`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetNfsShareList(struct _LIST_ENTRY *a1)
{
  int v2; // r12d
  DWORD IsClusterNode; // edi
  HANDLE ProcessHeap; // rax
  SIZE_T v5; // rdi
  unsigned int *v6; // rax
  unsigned int *v7; // rsi
  unsigned int v8; // eax
  HANDLE v9; // rax
  unsigned int v10; // ecx
  unsigned int *v11; // r13
  HANDLE v12; // rax
  struct _LIST_ENTRY *v13; // rax
  struct _LIST_ENTRY *v14; // r15
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v16; // rax
  int v17; // eax
  unsigned __int16 *v18; // r11
  struct _LIST_ENTRY *i; // rbx
  int v20; // eax
  struct _LIST_ENTRY *v21; // r8
  struct _LIST_ENTRY *v22; // rcx
  struct _LIST_ENTRY *v23; // rax
  struct _LIST_ENTRY *v24; // rdx
  struct _LIST_ENTRY *v25; // rdx
  struct _LIST_ENTRY *Flink; // r9
  struct _LIST_ENTRY *v27; // rcx
  struct _LIST_ENTRY *v28; // rax
  HANDLE v29; // rax
  char v30; // bl
  PCSZ *v31; // rax
  struct _LIST_ENTRY *v32; // rdx
  struct _LIST_ENTRY *v33; // rcx
  HANDLE v34; // rax
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-BCh]
  struct _LIST_ENTRY v38; // [rsp+48h] [rbp-B8h] BYREF
  DWORD nSize; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+5Ch] [rbp-A4h]
  unsigned int v41; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  char v43; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[16]; // [rsp+100h] [rbp+0h] BYREF

  v2 = 0;
  v40 = 0;
  v36 = 0;
  nSize = 16;
  a1->Blink = a1;
  a1->Flink = a1;
  v38.Blink = &v38;
  v38.Flink = &v38;
  IsClusterNode = NfsClusterIsClusterNode(a1, &v36);
  if ( IsClusterNode )
    goto LABEL_55;
  if ( v36 )
  {
    IsClusterNode = NfsGetSharesOnCurrentNode(&v38);
    if ( IsClusterNode )
      goto LABEL_55;
  }
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
  {
    IsClusterNode = GetLastError();
    if ( IsClusterNode )
      goto LABEL_55;
  }
  ProcessHeap = GetProcessHeap();
  v5 = 12;
  while ( 1 )
  {
    v6 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v5);
    v7 = v6;
    if ( !v6 )
    {
      IsClusterNode = 8;
LABEL_55:
      FreeNfsExportList(a1);
      FreeNfsExportList(&v38);
      return IsClusterNode;
    }
    v8 = NfsDeviceIoControl(L"\\\\.\\NfsSvr", 0x80000000, 0x100004C8u, 0, 0, v6, v5, 0);
    IsClusterNode = v8;
    if ( v8 != 234 )
      break;
    v5 = *v7;
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
    ProcessHeap = GetProcessHeap();
  }
  if ( !v8 )
  {
    v10 = v7[1];
    v41 = v10;
    if ( v10 )
    {
      v11 = v7 + 2;
      while ( 1 )
      {
        v37 = v8;
        if ( IsClusterNode )
          goto LABEL_52;
        if ( v8 >= v10 )
          goto LABEL_50;
        v12 = GetProcessHeap();
        v13 = (struct _LIST_ENTRY *)HeapAlloc(v12, 8u, 0x688u);
        v14 = v13;
        if ( !v13 )
        {
          IsClusterNode = 8;
          goto LABEL_52;
        }
        Blink = a1->Blink;
        if ( Blink->Flink != a1 )
          goto LABEL_48;
        v16 = v13 + 1;
        v16->Flink = a1;
        v16->Blink = Blink;
        Blink->Flink = v16;
        a1->Blink = v16;
        InitializeNfsExportEntry((struct _NFS_EXPORT *)v14);
        *v14 = *(struct _LIST_ENTRY *)v11;
        LOBYTE(v14[68].Blink) = 1;
        WORD1(v14[68].Blink) = 0;
        v17 = StringCchCopyW((unsigned __int16 *)&v14[2], 0x106u, (const unsigned __int16 *)((char *)v11 + v11[5] + 84));
        if ( v17 >= 0 )
        {
          v17 = StringCchCopyW(
                  (unsigned __int16 *)&v14[34].Blink + 2,
                  0x106u,
                  (const unsigned __int16 *)((char *)v11 + v11[7] + 84));
          if ( v17 >= 0 )
            v17 = StringCchCopyW(v18, 0x104u, Buffer);
        }
        IsClusterNode = NfsGetErrorFromHr(v17);
        if ( !IsClusterNode )
          break;
LABEL_45:
        v11 = (unsigned int *)((char *)v11 + v11[4]);
        v8 = v37 + 1;
        v10 = v41;
      }
      LODWORD(v14[67].Blink) = v11[13];
      HIDWORD(v14[67].Blink) = v11[14];
      LODWORD(v14[68].Flink) = v11[15];
      HIDWORD(v14[68].Flink) = 0;
      if ( v36 )
      {
        for ( i = v38.Flink; ; i = i->Flink )
        {
          if ( i == &v38 )
            goto LABEL_46;
          if ( !_wcsicmp((const wchar_t *)&i[1], (const wchar_t *)&v14[2]) )
            break;
        }
        LOBYTE(v14[68].Blink) = i[67].Blink;
        v20 = StringCchCopyW((unsigned __int16 *)&v14[68].Blink + 1, 0x104u, (const unsigned __int16 *)&i[67].Blink + 1);
        IsClusterNode = NfsGetErrorFromHr(v20);
        if ( !IsClusterNode )
        {
          v21 = (struct _LIST_ENTRY *)((char *)i + 1624);
          v22 = i[101].Blink;
          if ( v22 != (struct _LIST_ENTRY *)&i[101].Blink )
          {
            v23 = v22->Blink;
            if ( v23->Flink != v22
              || (v24 = v23->Blink, v24->Flink != v23)
              || (v22->Blink = v24,
                  v24->Flink = v22,
                  v25 = (struct _LIST_ENTRY *)((char *)v14 + 1640),
                  v14[102].Blink->Blink != (struct _LIST_ENTRY *)&v14[102].Blink)
              || (Flink = v14[103].Flink, Flink->Flink != v25)
              || v22->Flink->Blink != v22
              || v22->Blink->Flink != v22 )
            {
LABEL_48:
              __fastfail(3u);
            }
            Flink->Flink = v22;
            v14[103].Flink = v22->Blink;
            v22->Blink->Flink = v25;
            v22->Blink = Flink;
            i[102].Flink = v21;
            v21->Flink = v21;
            HIDWORD(v14[68].Flink) = HIDWORD(i[67].Flink);
          }
        }
        v27 = i->Flink;
        if ( i->Flink->Blink != i )
          goto LABEL_48;
        v28 = i->Blink;
        if ( v28->Flink != i )
          goto LABEL_48;
        v28->Flink = v27;
        v27->Blink = v28;
        FreeNfsExportFencingList((struct _LIST_ENTRY *)((char *)i + 1624));
        v29 = GetProcessHeap();
        HeapFree(v29, 0, &i[-1]);
      }
      else
      {
LABEL_46:
        v31 = (PCSZ *)ATL::CW2AEX<128>::CW2AEX<128>(&Block, (char *)v11 + v11[9] + 84);
        v2 |= 1u;
        v40 = v2;
        if ( !ParseExportFencingString(*v31, (struct _NFS_EXPORT *)v14) )
        {
          v30 = 1;
LABEL_40:
          if ( (v2 & 1) != 0 )
          {
            v2 &= ~1u;
            if ( Block != &v43 )
              free(Block);
          }
          if ( v30 )
            IsClusterNode = 13;
          goto LABEL_45;
        }
      }
      v30 = 0;
      goto LABEL_40;
    }
LABEL_50:
    v32 = v38.Flink;
    if ( v38.Flink != &v38 )
    {
      v33 = v38.Blink;
      a1->Blink->Flink = v38.Flink;
      v32->Blink = a1->Blink;
      v33->Flink = a1;
      a1->Blink = v33;
    }
  }
LABEL_52:
  if ( v7 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v7);
  }
  if ( IsClusterNode )
    goto LABEL_55;
  return IsClusterNode;
}

```

## disassembly

```asm
0x18001e418  push    rbp
0x18001e41a  push    rbx
0x18001e41b  push    rsi
0x18001e41c  push    rdi
0x18001e41d  push    r12
0x18001e41f  push    r13
0x18001e421  push    r14
0x18001e423  push    r15
0x18001e425  lea     rbp, [rsp-38h]
0x18001e42a  sub     rsp, 138h
0x18001e431  mov     rax, cs:__security_cookie
0x18001e438  xor     rax, rsp
0x18001e43b  mov     [rbp+70h+var_50], rax
0x18001e43f  mov     r14, rcx
0x18001e442  xor     r12d, r12d
0x18001e445  mov     [rsp+170h+var_114], r12d
0x18001e44a  mov     [rsp+170h+var_130], r12d
0x18001e44f  mov     [rsp+170h+nSize], 10h
0x18001e457  mov     [rcx+8], rcx
0x18001e45b  mov     [rcx], rcx
0x18001e45e  lea     rax, [rsp+170h+var_128]
0x18001e463  mov     [rsp+170h+var_128.Blink], rax
0x18001e468  lea     rax, [rsp+170h+var_128]
0x18001e46d  mov     [rsp+170h+var_128.Flink], rax
0x18001e472  lea     rdx, [rsp+170h+var_130]
0x18001e477  call    NfsClusterIsClusterNode
0x18001e47c  mov     edi, eax
0x18001e47e  test    eax, eax
0x18001e480  jnz     loc_18001E87B
0x18001e486  cmp     [rsp+170h+var_130], r12d
0x18001e48b  jz      short loc_18001E4A1
0x18001e48d  lea     rcx, [rsp+170h+var_128]; struct _LIST_ENTRY *
0x18001e492  call    ?NfsGetSharesOnCurrentNode@@YAKPEAU_LIST_ENTRY@@@Z; NfsGetSharesOnCurrentNode(_LIST_ENTRY *)
0x18001e497  mov     edi, eax
0x18001e499  test    eax, eax
0x18001e49b  jnz     loc_18001E87B
0x18001e4a1  lea     r8, [rsp+170h+nSize]; nSize
0x18001e4a6  lea     rdx, [rbp+70h+Buffer]; lpBuffer
0x18001e4aa  mov     ecx, 4; NameType
0x18001e4af  call    cs:__imp_GetComputerNameExW
0x18001e4b5  test    eax, eax
0x18001e4b7  jnz     short loc_18001E4C9
0x18001e4b9  call    cs:__imp_GetLastError
0x18001e4bf  mov     edi, eax
0x18001e4c1  test    eax, eax
0x18001e4c3  jnz     loc_18001E87B
0x18001e4c9  call    cs:__imp_GetProcessHeap
0x18001e4cf  mov     edi, 0Ch
0x18001e4d4  mov     rcx, rax; hHeap
0x18001e4d7  mov     r8, rdi; dwBytes
0x18001e4da  mov     ebx, 8
0x18001e4df  mov     edx, ebx; dwFlags
0x18001e4e1  call    cs:__imp_HeapAlloc
0x18001e4e7  mov     rsi, rax
0x18001e4ea  test    rax, rax
0x18001e4ed  jnz     short loc_18001E4F6
0x18001e4ef  mov     edi, ebx
0x18001e4f1  jmp     loc_18001E87B
0x18001e4f6  mov     [rsp+170h+var_138], r12; unsigned int *
0x18001e4fb  mov     [rsp+170h+var_140], edi; unsigned int
0x18001e4ff  mov     [rsp+170h+var_148], rsi; void *
0x18001e504  mov     [rsp+170h+var_150], r12d; unsigned int
0x18001e509  xor     r9d, r9d; void *
0x18001e50c  mov     edx, 80000000h; unsigned int
0x18001e511  mov     r8d, 100004C8h; unsigned int
0x18001e517  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18001e51e  call    ?NfsDeviceIoControl@@YAKPEBGKKPEAXK1KPEAK@Z; NfsDeviceIoControl(ushort const *,ulong,ulong,void *,ulong,void *,ulong,ulong *)
0x18001e523  mov     edi, eax
0x18001e525  cmp     eax, 0EAh
0x18001e52a  jnz     short loc_18001E54A
0x18001e52c  mov     edi, [rsi]
0x18001e52e  call    cs:__imp_GetProcessHeap
0x18001e534  mov     rcx, rax; hHeap
0x18001e537  mov     r8, rsi; lpMem
0x18001e53a  xor     edx, edx; dwFlags
0x18001e53c  call    cs:__imp_HeapFree
0x18001e542  call    cs:__imp_GetProcessHeap
0x18001e548  jmp     short loc_18001E4D4
0x18001e54a  test    eax, eax
0x18001e54c  jnz     loc_18001E85E
0x18001e552  mov     ecx, [rsi+4]
0x18001e555  mov     [rsp+170h+var_110], ecx
0x18001e559  test    ecx, ecx
0x18001e55b  jz      loc_18001E834
0x18001e561  lea     r13, [rsi+8]
0x18001e565  mov     [rsp+170h+var_12C], eax
0x18001e569  test    edi, edi
0x18001e56b  jnz     loc_18001E85E
0x18001e571  cmp     eax, ecx
0x18001e573  jnb     loc_18001E834
0x18001e579  call    cs:__imp_GetProcessHeap
0x18001e57f  mov     rcx, rax; hHeap
0x18001e582  mov     r8d, 688h; dwBytes
0x18001e588  mov     edx, ebx; dwFlags
0x18001e58a  call    cs:__imp_HeapAlloc
0x18001e590  mov     r15, rax
0x18001e593  test    rax, rax
0x18001e596  jz      loc_18001E830
0x18001e59c  mov     rcx, [r14+8]
0x18001e5a0  cmp     [rcx], r14
0x18001e5a3  jnz     loc_18001E829
0x18001e5a9  add     rax, 10h
0x18001e5ad  mov     [rax], r14
0x18001e5b0  mov     [rax+8], rcx
0x18001e5b4  mov     [rcx], rax
0x18001e5b7  mov     [r14+8], rax
0x18001e5bb  mov     rcx, r15; struct _NFS_EXPORT *
0x18001e5be  call    ?InitializeNfsExportEntry@@YAXPEAU_NFS_EXPORT@@@Z; InitializeNfsExportEntry(_NFS_EXPORT *)
0x18001e5c3  movups  xmm0, xmmword ptr [r13+0]
0x18001e5c8  movdqu  xmmword ptr [r15], xmm0
0x18001e5cd  mov     byte ptr [r15+448h], 1
0x18001e5d5  lea     r11, [r15+44Ah]
0x18001e5dc  xor     eax, eax
0x18001e5de  mov     [r11], ax
0x18001e5e2  lea     rcx, [r15+20h]; unsigned __int16 *
0x18001e5e6  mov     r8d, [r13+14h]
0x18001e5ea  add     r8, 54h ; 'T'
0x18001e5ee  add     r8, r13; unsigned __int16 *
0x18001e5f1  mov     edi, 106h
0x18001e5f6  mov     edx, edi; unsigned __int64
0x18001e5f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e5fd  test    eax, eax
0x18001e5ff  js      short loc_18001E62D
0x18001e601  mov     r8d, [r13+1Ch]
0x18001e605  add     r8, 54h ; 'T'
0x18001e609  add     r8, r13; unsigned __int16 *
0x18001e60c  lea     rcx, [r15+22Ch]; unsigned __int16 *
0x18001e613  mov     edx, edi; unsigned __int64
0x18001e615  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e61a  test    eax, eax
0x18001e61c  js      short loc_18001E62D
0x18001e61e  lea     r8, [rbp+70h+Buffer]; unsigned __int16 *
0x18001e622  lea     edx, [rdi-2]; unsigned __int64
0x18001e625  mov     rcx, r11; unsigned __int16 *
0x18001e628  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e62d  mov     ecx, eax; int
0x18001e62f  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001e634  mov     edi, eax
0x18001e636  test    eax, eax
0x18001e638  jnz     loc_18001E7E1
0x18001e63e  mov     eax, [r13+34h]
0x18001e642  mov     [r15+438h], eax
0x18001e649  mov     eax, [r13+38h]
0x18001e64d  mov     [r15+43Ch], eax
0x18001e654  mov     eax, [r13+3Ch]
0x18001e658  mov     [r15+440h], eax
0x18001e65f  mov     [r15+444h], edi
0x18001e666  cmp     [rsp+170h+var_130], edi
0x18001e66a  jz      loc_18001E7F7
0x18001e670  mov     rbx, [rsp+170h+var_128.Flink]
0x18001e675  lea     rax, [rsp+170h+var_128]
0x18001e67a  cmp     rbx, rax
0x18001e67d  jz      loc_18001E7F7
0x18001e683  lea     rcx, [rbx+10h]; String1
0x18001e687  lea     rdx, [r15+20h]; String2
0x18001e68b  call    cs:__imp__wcsicmp
0x18001e691  test    eax, eax
0x18001e693  jz      short loc_18001E69A
0x18001e695  mov     rbx, [rbx]
0x18001e698  jmp     short loc_18001E675
0x18001e69a  mov     al, [rbx+438h]
0x18001e6a0  mov     [r15+448h], al
0x18001e6a7  lea     r8, [rbx+43Ah]; unsigned __int16 *
0x18001e6ae  mov     edx, 104h; unsigned __int64
0x18001e6b3  lea     rcx, [r15+44Ah]; unsigned __int16 *
0x18001e6ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e6bf  mov     ecx, eax; int
0x18001e6c1  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001e6c6  mov     edi, eax
0x18001e6c8  test    eax, eax
0x18001e6ca  jnz     loc_18001E76F
0x18001e6d0  lea     r8, [rbx+658h]
0x18001e6d7  mov     rcx, [r8]
0x18001e6da  cmp     rcx, r8
0x18001e6dd  jz      loc_18001E76F
0x18001e6e3  mov     rax, [rcx+8]
0x18001e6e7  cmp     [rax], rcx
0x18001e6ea  jnz     loc_18001E829
0x18001e6f0  mov     rdx, [rax+8]
0x18001e6f4  cmp     [rdx], rax
0x18001e6f7  jnz     loc_18001E829
0x18001e6fd  mov     [rcx+8], rdx
0x18001e701  mov     [rdx], rcx
0x18001e704  lea     rdx, [r15+668h]
0x18001e70b  mov     rax, [rdx]
0x18001e70e  cmp     [rax+8], rdx
0x18001e712  jnz     loc_18001E829
0x18001e718  mov     r9, [r15+670h]
0x18001e71f  cmp     [r9], rdx
0x18001e722  jnz     loc_18001E829
0x18001e728  mov     rax, [rcx]
0x18001e72b  cmp     [rax+8], rcx
0x18001e72f  jnz     loc_18001E829
0x18001e735  mov     rax, [rcx+8]
0x18001e739  cmp     [rax], rcx
0x18001e73c  jnz     loc_18001E829
0x18001e742  mov     [r9], rcx
0x18001e745  mov     rax, [rcx+8]
0x18001e749  mov     [rdx+8], rax
0x18001e74d  mov     rax, [rcx+8]
0x18001e751  mov     [rax], rdx
0x18001e754  mov     [rcx+8], r9
0x18001e758  mov     [rbx+660h], r8
0x18001e75f  mov     [r8], r8
0x18001e762  mov     eax, [rbx+434h]
0x18001e768  mov     [r15+444h], eax
0x18001e76f  mov     rcx, [rbx]
0x18001e772  cmp     [rcx+8], rbx
0x18001e776  jnz     loc_18001E829
0x18001e77c  mov     rax, [rbx+8]
0x18001e780  cmp     [rax], rbx
0x18001e783  jnz     loc_18001E829
0x18001e789  mov     [rax], rcx
0x18001e78c  mov     [rcx+8], rax
0x18001e790  lea     rcx, [rbx+658h]; struct _LIST_ENTRY *
0x18001e797  call    ?FreeNfsExportFencingList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportFencingList(_LIST_ENTRY *)
0x18001e79c  call    cs:__imp_GetProcessHeap
0x18001e7a2  mov     rcx, rax; hHeap
0x18001e7a5  lea     r8, [rbx-10h]; lpMem
0x18001e7a9  xor     edx, edx; dwFlags
0x18001e7ab  call    cs:__imp_HeapFree
0x18001e7b1  nop
0x18001e7b2  xor     bl, bl
0x18001e7b4  test    r12b, 1
0x18001e7b8  jz      short loc_18001E7D4
0x18001e7ba  and     r12d, 0FFFFFFFEh
0x18001e7be  mov     rcx, [rsp+170h+Block]; Block
0x18001e7c3  lea     rax, [rsp+170h+var_F8]
0x18001e7c8  cmp     rcx, rax
0x18001e7cb  jz      short loc_18001E7D4
0x18001e7cd  call    cs:__imp_free
0x18001e7d3  nop
0x18001e7d4  mov     eax, 0Dh
0x18001e7d9  test    bl, bl
0x18001e7db  cmovnz  edi, eax
0x18001e7de  lea     ebx, [rax-5]
0x18001e7e1  mov     eax, [r13+10h]
0x18001e7e5  add     r13, rax
0x18001e7e8  mov     eax, [rsp+170h+var_12C]
0x18001e7ec  inc     eax
0x18001e7ee  mov     ecx, [rsp+170h+var_110]
0x18001e7f2  jmp     loc_18001E565
0x18001e7f7  mov     edx, [r13+24h]
0x18001e7fb  add     rdx, 54h ; 'T'
0x18001e7ff  add     rdx, r13
0x18001e802  lea     rcx, [rsp+170h+Block]
0x18001e807  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x18001e80c  nop
0x18001e80d  or      r12d, 1
0x18001e811  mov     [rsp+170h+var_114], r12d
0x18001e816  mov     rdx, r15; struct _NFS_EXPORT *
0x18001e819  mov     rcx, [rax]; SourceString
0x18001e81c  call    ?ParseExportFencingString@@YAEPEBDPEAU_NFS_EXPORT@@@Z; ParseExportFencingString(char const *,_NFS_EXPORT *)
0x18001e821  test    al, al
0x18001e823  jnz     short loc_18001E7B2
0x18001e825  mov     bl, 1
0x18001e827  jmp     short loc_18001E7B4
0x18001e829  mov     ecx, 3
0x18001e82e  int     29h; Win8: RtlFailFast(ecx)
0x18001e830  mov     edi, ebx
0x18001e832  jmp     short loc_18001E85E
0x18001e834  mov     rdx, [rsp+170h+var_128.Flink]
0x18001e839  lea     rax, [rsp+170h+var_128]
0x18001e83e  cmp     rdx, rax
0x18001e841  jz      short loc_18001E85E
0x18001e843  mov     rcx, [rsp+170h+var_128.Blink]
0x18001e848  mov     rax, [r14+8]
0x18001e84c  mov     [rax], rdx
0x18001e84f  mov     rax, [r14+8]
0x18001e853  mov     [rdx+8], rax
0x18001e857  mov     [rcx], r14
0x18001e85a  mov     [r14+8], rcx
0x18001e85e  test    rsi, rsi
0x18001e861  jz      short loc_18001E877
0x18001e863  call    cs:__imp_GetProcessHeap
0x18001e869  mov     rcx, rax; hHeap
0x18001e86c  mov     r8, rsi; lpMem
0x18001e86f  xor     edx, edx; dwFlags
0x18001e871  call    cs:__imp_HeapFree
0x18001e877  test    edi, edi
0x18001e879  jz      short loc_18001E88D
0x18001e87b  mov     rcx, r14; struct _LIST_ENTRY *
0x18001e87e  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18001e883  lea     rcx, [rsp+170h+var_128]; struct _LIST_ENTRY *
0x18001e888  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18001e88d  mov     eax, edi
0x18001e88f  mov     rcx, [rbp+70h+var_50]
0x18001e893  xor     rcx, rsp; StackCookie
0x18001e896  call    __security_check_cookie
0x18001e89b  add     rsp, 138h
0x18001e8a2  pop     r15
0x18001e8a4  pop     r14
0x18001e8a6  pop     r13
0x18001e8a8  pop     r12
0x18001e8aa  pop     rdi
0x18001e8ab  pop     rsi
0x18001e8ac  pop     rbx
0x18001e8ad  pop     rbp
0x18001e8ae  retn
```
