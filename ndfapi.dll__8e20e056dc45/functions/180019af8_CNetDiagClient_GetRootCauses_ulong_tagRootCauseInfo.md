# CNetDiagClient::GetRootCauses(ulong *,tagRootCauseInfo * *)

- ea: `0x180019af8`
- end: `0x18001a016`
- name: `?GetRootCauses@CNetDiagClient@@QEAAJPEAKPEAPEAUtagRootCauseInfo@@@Z`
- size: `1310`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, unsigned int *, struct tagRootCauseInfo **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014340`
- `0x18001b564`

## callees

- `0x180008b08`
- `0x180008c08`
- `0x18000e830`
- `0x18000f1d0`
- `0x18000f78c`
- `0x180018ed4`
- `0x18001977c`
- `0x180019af8`
- `0x18001a884`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180019d06`
- `ole32!CoTaskMemAlloc` at `0x180019e57`
- `ole32!CoTaskMemAlloc` at `0x180019e81`
- `ole32!CoTaskMemAlloc` at `0x180019f34`
- `ole32!CoTaskMemAlloc` at `0x180019d06`
- `ole32!CoTaskMemAlloc` at `0x180019e57`
- `ole32!CoTaskMemAlloc` at `0x180019e81`
- `ole32!CoTaskMemAlloc` at `0x180019f34`
- `ole32!CoCreateInstance` at `0x180019df1`
- `ole32!CoCreateInstance` at `0x180019df1`
- `ole32!CoInitialize` at `0x180019da4`
- `ole32!CoInitialize` at `0x180019da4`
- `ole32!CoUninitialize` at `0x180019cd7`
- `ole32!CoUninitialize` at `0x180019e35`
- `ole32!CoUninitialize` at `0x180019cd7`
- `ole32!CoUninitialize` at `0x180019e35`
- `ole32!CoInitializeEx` at `0x180019b45`
- `ole32!CoInitializeEx` at `0x180019bdf`
- `ole32!CoInitializeEx` at `0x180019b45`
- `ole32!CoInitializeEx` at `0x180019bdf`
- `ole32!CoTaskMemFree` at `0x180019f61`
- `ole32!CoTaskMemFree` at `0x180019f61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNetDiagClient::GetRootCauses(CNetDiagClient *this, unsigned int *a2, struct tagRootCauseInfo **a3)
{
  unsigned int v3; // r15d
  struct tagRootCauseInfo **v4; // r12
  signed int updated; // ebx
  BOOL v8; // esi
  unsigned int v9; // ebp
  HRESULT v10; // esi
  int v11; // r8d
  unsigned int v12; // r14d
  __int64 v13; // r15
  struct tagRepairInfo *v14; // rdx
  int v15; // edx
  unsigned int v16; // ebp
  unsigned int v17; // ebp
  unsigned __int16 **v18; // rbx
  int v19; // r14d
  unsigned int v20; // r14d
  SIZE_T v21; // rsi
  struct tagRootCauseInfo *v22; // rax
  struct tagRootCauseInfo *v23; // rbp
  __int64 v24; // rsi
  __int64 v25; // rcx
  unsigned int v26; // edx
  struct tagRootCauseInfo *v27; // rcx
  HRESULT v28; // eax
  HRESULT v29; // ebx
  int v30; // edi
  __int64 v32; // rbx
  _BYTE *v33; // rax
  _BYTE *v34; // rdi
  __int64 v35; // rbx
  _BYTE *v36; // rax
  CNetDiagClient *v37; // rcx
  unsigned int v38; // r9d
  struct tagRepairInfo *v39; // rsi
  CNetDiagClient *v40; // rcx
  unsigned int v41; // r9d
  unsigned __int16 **v42; // r14
  const unsigned __int16 *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rbp
  unsigned __int16 *v46; // rax
  __int64 v47; // rax
  int v48; // [rsp+70h] [rbp+8h] BYREF
  struct tagRootCauseInfo **v49; // [rsp+80h] [rbp+18h]
  LPVOID ppv; // [rsp+88h] [rbp+20h] BYREF

  v49 = a3;
  v3 = 0;
  v4 = a3;
  updated = 0;
  v8 = 0;
  if ( !*((_DWORD *)this + 760) && (*((_BYTE *)this + 3044) & 2) != 0 )
  {
    v9 = 0;
    v10 = CoInitializeEx(0, 0);
    if ( *((_DWORD *)this + 758) )
    {
      while ( 1 )
      {
        v12 = 0;
        v13 = 88LL * v9;
        if ( *(_WORD *)((char *)this + v13 + 2056) )
          break;
LABEL_8:
        if ( ++v9 >= *((_DWORD *)this + 758) )
          goto LABEL_9;
      }
      while ( 1 )
      {
        v14 = (struct tagRepairInfo *)(*(_QWORD *)((char *)this + v13 + 2048) + 120LL * v12);
        if ( (v14->flags & 0x80000000) != 0 )
        {
          updated = CNetDiagClient::UpdateCatchAllInfo(this, v14, v11);
          if ( updated < 0 )
            break;
        }
        if ( ++v12 >= *(unsigned __int16 *)((char *)this + v13 + 2056) )
          goto LABEL_8;
      }
LABEL_9:
      v3 = 0;
    }
    if ( updated < 0 )
      return (unsigned int)updated;
    CNetDiagClient::ApplyRootCauseFilter(this);
    v8 = v10 >= 0;
  }
  if ( !*((_DWORD *)this + 820) )
  {
    if ( !v8 )
      v8 = CoInitializeEx(0, 0) >= 0;
    v15 = ReplaceXML((unsigned __int16 **)this + 6);
    if ( v15 >= 0 )
    {
      v16 = 0;
      if ( *((_DWORD *)this + 492) )
      {
        do
        {
          v15 = ReplaceXML((unsigned __int16 **)this + 19 * v16 + 24);
          updated = v15;
          if ( v15 < 0 )
            return (unsigned int)updated;
        }
        while ( ++v16 < *((_DWORD *)this + 492) );
      }
      v17 = 0;
      if ( *((_DWORD *)this + 758) )
      {
        while ( 1 )
        {
          v18 = (unsigned __int16 **)((char *)this + 88 * v17);
          if ( !*((_DWORD *)this + 760) || *((int *)v18 + 506) >= 0 )
          {
            v15 = ReplaceXML(v18 + 250);
            if ( v15 < 0 )
              goto LABEL_27;
            v19 = 0;
            if ( *((_WORD *)v18 + 1028) )
              break;
          }
LABEL_26:
          if ( ++v17 >= *((_DWORD *)this + 758) )
            goto LABEL_27;
        }
        while ( 1 )
        {
          v15 = ReplaceXML((unsigned __int16 **)&v18[256][60 * v19 + 12]);
          if ( v15 < 0 )
            break;
          if ( ++v19 >= (unsigned int)*((unsigned __int16 *)v18 + 1028) )
            goto LABEL_26;
        }
LABEL_27:
        v4 = v49;
      }
    }
    updated = v15;
    if ( v15 < 0 )
      return (unsigned int)updated;
  }
  if ( v8 )
    CoUninitialize();
  v20 = *(_DWORD *)((char *)this + (*((_DWORD *)this + 760) != 0 ? 4 : 0) + 3032);
  if ( !v20 )
  {
    v48 = 0;
    v28 = CoInitialize(0);
    ppv = 0;
    v29 = v28;
    if ( v28 == -2147417850 )
    {
      v30 = 0;
    }
    else
    {
      if ( v28 < 0 )
        goto LABEL_54;
      v30 = 1;
      if ( v28 )
        goto LABEL_50;
    }
    v29 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, &ppv);
    if ( !v29 )
      v29 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 104LL))(ppv, &v48);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( !v30 )
    {
LABEL_51:
      if ( !v29 && (v48 & 0x440) != 0 )
        return 0;
LABEL_54:
      v32 = 64;
      v33 = CoTaskMemAlloc(0x40u);
      v34 = v33;
      if ( v33 )
      {
        do
        {
          *v33++ = 0;
          --v32;
        }
        while ( v32 );
        v35 = 120;
        v36 = CoTaskMemAlloc(0x78u);
        *((_QWORD *)v34 + 6) = v36;
        if ( v36 )
        {
          do
          {
            *v36++ = 0;
            --v35;
          }
          while ( v35 );
          v39 = (struct tagRepairInfo *)*((_QWORD *)v34 + 6);
          updated = CNetDiagClient::LoadStringWithAlloc(v37, 0x9CC2u, (unsigned __int16 **)v34, v38);
          if ( updated >= 0 )
          {
            updated = CNetDiagClient::LoadStringWithAlloc(
                        v40,
                        0x9CC3u,
                        (unsigned __int16 **)(*((_QWORD *)v34 + 6) + 24LL),
                        v41);
            if ( updated >= 0 )
            {
              v42 = (unsigned __int16 **)(*((_QWORD *)v34 + 6) + 16LL);
              if ( *((_QWORD *)v34 + 6) == -16 )
              {
                updated = -2147024809;
              }
              else
              {
                v43 = L"PushButtonReset";
                v44 = 65534;
                do
                {
                  if ( !*v43 )
                    break;
                  ++v43;
                  --v44;
                }
                while ( v44 );
                updated = v44 == 0 ? 0x80070057 : 0;
                v45 = (65534 - v44) & -(__int64)(v44 != 0);
                if ( v44 )
                {
                  v46 = (unsigned __int16 *)CoTaskMemAlloc(2 * v45 + 2);
                  *v42 = v46;
                  if ( v46 )
                  {
                    updated = StringCchCopyW(v46, v45 + 1, L"PushButtonReset");
                    if ( updated >= 0 )
                    {
                      v47 = *((_QWORD *)v34 + 6);
                      *((_WORD *)v34 + 28) = 1;
                      *((_DWORD *)v34 + 6) = 2;
                      *(_OWORD *)(v34 + 8) = xmmword_180027A40;
                      *(_DWORD *)(v47 + 36) = 5;
                      *(_DWORD *)(*((_QWORD *)v34 + 6) + 40LL) = 0x8000000;
                      *(_OWORD *)*((_QWORD *)v34 + 6) = xmmword_180027A30;
                      *(_DWORD *)(*((_QWORD *)v34 + 6) + 32LL) = 26;
                      *(_DWORD *)(*((_QWORD *)v34 + 6) + 56LL) = 1;
                      *(_WORD *)(*((_QWORD *)v34 + 6) + 112LL) = 1;
                      *v4 = (struct tagRootCauseInfo *)v34;
                      *a2 = 1;
                      return (unsigned int)updated;
                    }
                  }
                  else
                  {
                    updated = -2147024882;
                  }
                }
              }
            }
          }
          if ( v39 )
          {
            FreeRepairInfos(v39, 1u, 0);
            CoTaskMemFree(v39);
          }
          v26 = 1;
          v27 = (struct tagRootCauseInfo *)v34;
          goto LABEL_72;
        }
        FreeRootCauseInfos((struct tagRootCauseInfo *)v34, 1u, 1);
      }
      return 2147942414LL;
    }
LABEL_50:
    CoUninitialize();
    goto LABEL_51;
  }
  v21 = (unsigned __int64)v20 << 6;
  v22 = (struct tagRootCauseInfo *)CoTaskMemAlloc(v21);
  v23 = v22;
  if ( !v22 )
    return 2147942414LL;
  for ( ; v21; --v21 )
  {
    LOBYTE(v22->pwszDescription) = 0;
    v22 = (struct tagRootCauseInfo *)((char *)v22 + 1);
  }
  v24 = 0;
  if ( *((_DWORD *)this + 758) )
  {
    while ( 1 )
    {
      if ( *((int *)this + 22 * v24 + 506) >= 0 )
      {
        v25 = v3++;
        updated = CopyRootCauseInfo(
                    &v23[v25],
                    (const struct tagRootCauseInfo *)((char *)this + 88 * (unsigned int)v24 + 2000));
        if ( updated < 0 )
          break;
      }
      v24 = (unsigned int)(v24 + 1);
      if ( (unsigned int)v24 >= *((_DWORD *)this + 758) )
        goto LABEL_39;
    }
    v26 = v20;
    v27 = v23;
LABEL_72:
    FreeRootCauseInfos(v27, v26, 1);
    return (unsigned int)updated;
  }
LABEL_39:
  *v4 = v23;
  *a2 = v20;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180019af8  mov     [rsp+arg_8], rbx
0x180019afd  mov     [rsp+arg_10], r8
0x180019b02  push    rbp
0x180019b03  push    rsi
0x180019b04  push    rdi
0x180019b05  push    r12
0x180019b07  push    r13
0x180019b09  push    r14
0x180019b0b  push    r15
0x180019b0d  sub     rsp, 30h
0x180019b11  xor     r15d, r15d
0x180019b14  mov     r12, r8
0x180019b17  mov     r13, rdx
0x180019b1a  mov     rdi, rcx
0x180019b1d  mov     ebx, r15d
0x180019b20  mov     esi, r15d
0x180019b23  lea     ebp, [r15+1]
0x180019b27  cmp     [rcx+0BE0h], r15d
0x180019b2e  jnz     loc_180019BCA
0x180019b34  test    byte ptr [rcx+0BE4h], 2
0x180019b3b  jz      loc_180019BCA
0x180019b41  xor     edx, edx; dwCoInit
0x180019b43  xor     ecx, ecx; pvReserved
0x180019b45  call    cs:__imp_CoInitializeEx
0x180019b4b  mov     ebp, r15d
0x180019b4e  mov     esi, eax
0x180019b50  cmp     [rdi+0BD8h], r15d
0x180019b57  jbe     short loc_180019BB0
0x180019b59  mov     eax, ebp
0x180019b5b  xor     r14d, r14d
0x180019b5e  imul    r15, rax, 58h ; 'X'
0x180019b62  xor     eax, eax
0x180019b64  cmp     ax, [r15+rdi+808h]
0x180019b6d  jnb     short loc_180019BA3
0x180019b6f  mov     eax, r14d
0x180019b72  imul    rdx, rax, 78h ; 'x'
0x180019b76  add     rdx, [r15+rdi+800h]; struct tagRepairInfo *
0x180019b7e  cmp     dword ptr [rdx+28h], 0
0x180019b82  jge     short loc_180019B92
0x180019b84  mov     rcx, rdi; this
0x180019b87  call    ?UpdateCatchAllInfo@CNetDiagClient@@IEAAJAEAUtagRepairInfo@@H@Z; CNetDiagClient::UpdateCatchAllInfo(tagRepairInfo &,int)
0x180019b8c  mov     ebx, eax
0x180019b8e  test    eax, eax
0x180019b90  js      short loc_180019BAD
0x180019b92  movzx   eax, word ptr [r15+rdi+808h]
0x180019b9b  inc     r14d
0x180019b9e  cmp     r14d, eax
0x180019ba1  jb      short loc_180019B6F
0x180019ba3  inc     ebp
0x180019ba5  cmp     ebp, [rdi+0BD8h]
0x180019bab  jb      short loc_180019B59
0x180019bad  xor     r15d, r15d
0x180019bb0  test    ebx, ebx
0x180019bb2  js      loc_180019F74
0x180019bb8  mov     rcx, rdi; this
0x180019bbb  call    ?ApplyRootCauseFilter@CNetDiagClient@@IEAAJXZ; CNetDiagClient::ApplyRootCauseFilter(void)
0x180019bc0  not     esi
0x180019bc2  mov     ebp, 1
0x180019bc7  shr     esi, 1Fh
0x180019bca  cmp     [rdi+0CD0h], r15d
0x180019bd1  jnz     loc_180019CD3
0x180019bd7  test    esi, esi
0x180019bd9  jnz     short loc_180019BEA
0x180019bdb  xor     edx, edx; dwCoInit
0x180019bdd  xor     ecx, ecx; pvReserved
0x180019bdf  call    cs:__imp_CoInitializeEx
0x180019be5  test    eax, eax
0x180019be7  cmovns  esi, ebp
0x180019bea  lea     rcx, [rdi+30h]; unsigned __int16 **
0x180019bee  call    ?ReplaceXML@@YAJPEAPEAG@Z; ReplaceXML(ushort * *)
0x180019bf3  mov     edx, eax
0x180019bf5  test    eax, eax
0x180019bf7  js      loc_180019CC9
0x180019bfd  mov     ebp, r15d
0x180019c00  cmp     [rdi+7B0h], r15d
0x180019c07  jbe     short loc_180019C37
0x180019c09  lea     r14, [rdi+0C0h]
0x180019c10  mov     eax, ebp
0x180019c12  imul    rcx, rax, 98h
0x180019c19  add     rcx, r14; unsigned __int16 **
0x180019c1c  call    ?ReplaceXML@@YAJPEAPEAG@Z; ReplaceXML(ushort * *)
0x180019c21  mov     edx, eax
0x180019c23  mov     ebx, eax
0x180019c25  test    eax, eax
0x180019c27  js      loc_180019F74
0x180019c2d  inc     ebp
0x180019c2f  cmp     ebp, [rdi+7B0h]
0x180019c35  jb      short loc_180019C10
0x180019c37  mov     ebp, r15d
0x180019c3a  cmp     [rdi+0BD8h], r15d
0x180019c41  jbe     loc_180019CC9
0x180019c47  mov     r12d, 1
0x180019c4d  mov     eax, ebp
0x180019c4f  imul    rbx, rax, 58h ; 'X'
0x180019c53  add     rbx, rdi
0x180019c56  cmp     [rdi+0BE0h], r15d
0x180019c5d  jz      short loc_180019C68
0x180019c5f  cmp     [rbx+7E8h], r15d
0x180019c66  jl      short loc_180019CB6
0x180019c68  lea     rcx, [rbx+7D0h]; unsigned __int16 **
0x180019c6f  call    ?ReplaceXML@@YAJPEAPEAG@Z; ReplaceXML(ushort * *)
0x180019c74  mov     edx, eax
0x180019c76  test    eax, eax
0x180019c78  js      short loc_180019CC1
0x180019c7a  mov     r14d, r15d
0x180019c7d  cmp     r15w, [rbx+808h]
0x180019c85  jnb     short loc_180019CB6
0x180019c87  mov     eax, r14d
0x180019c8a  imul    rcx, rax, 78h ; 'x'
0x180019c8e  mov     rax, [rbx+800h]
0x180019c95  add     rax, 18h
0x180019c99  add     rcx, rax; unsigned __int16 **
0x180019c9c  call    ?ReplaceXML@@YAJPEAPEAG@Z; ReplaceXML(ushort * *)
0x180019ca1  mov     edx, eax
0x180019ca3  test    eax, eax
0x180019ca5  js      short loc_180019CC1
0x180019ca7  movzx   eax, word ptr [rbx+808h]
0x180019cae  add     r14d, r12d
0x180019cb1  cmp     r14d, eax
0x180019cb4  jb      short loc_180019C87
0x180019cb6  add     ebp, r12d
0x180019cb9  cmp     ebp, [rdi+0BD8h]
0x180019cbf  jb      short loc_180019C4D
0x180019cc1  mov     r12, [rsp+68h+arg_10]
0x180019cc9  mov     ebx, edx
0x180019ccb  test    edx, edx
0x180019ccd  js      loc_180019F74
0x180019cd3  test    esi, esi
0x180019cd5  jz      short loc_180019CDD
0x180019cd7  call    cs:__imp_CoUninitialize
0x180019cdd  mov     eax, [rdi+0BE0h]
0x180019ce3  neg     eax
0x180019ce5  sbb     rcx, rcx
0x180019ce8  and     ecx, 4
0x180019ceb  mov     r14d, [rcx+rdi+0BD8h]
0x180019cf3  test    r14d, r14d
0x180019cf6  jz      loc_180019D9D
0x180019cfc  mov     esi, r14d
0x180019cff  shl     rsi, 6
0x180019d03  mov     rcx, rsi; cb
0x180019d06  call    cs:__imp_CoTaskMemAlloc
0x180019d0c  mov     rbp, rax
0x180019d0f  test    rax, rax
0x180019d12  jz      loc_180019E65
0x180019d18  mov     r8d, 1
0x180019d1e  test    rsi, rsi
0x180019d21  jz      short loc_180019D2E
0x180019d23  mov     byte ptr [rax], 0
0x180019d26  add     rax, r8
0x180019d29  sub     rsi, r8
0x180019d2c  jnz     short loc_180019D23
0x180019d2e  xor     esi, esi
0x180019d30  cmp     [rdi+0BD8h], esi
0x180019d36  jbe     short loc_180019D7F
0x180019d38  lea     rax, [rsi+17h]
0x180019d3c  mov     edx, esi
0x180019d3e  imul    rcx, rax, 58h ; 'X'
0x180019d42  cmp     dword ptr [rcx+rdi], 0
0x180019d46  jl      short loc_180019D74
0x180019d48  imul    rdx, 58h ; 'X'
0x180019d4c  mov     ecx, r15d
0x180019d4f  add     r15d, r8d
0x180019d52  add     rdx, 7D0h
0x180019d59  shl     rcx, 6
0x180019d5d  add     rdx, rdi; struct tagRootCauseInfo *
0x180019d60  add     rcx, rbp; struct tagRootCauseInfo *
0x180019d63  call    ?CopyRootCauseInfo@@YAJPEAUtagRootCauseInfo@@PEBU1@@Z; CopyRootCauseInfo(tagRootCauseInfo *,tagRootCauseInfo const *)
0x180019d68  mov     ebx, eax
0x180019d6a  test    eax, eax
0x180019d6c  js      short loc_180019D8C
0x180019d6e  mov     r8d, 1
0x180019d74  add     esi, r8d
0x180019d77  cmp     esi, [rdi+0BD8h]
0x180019d7d  jb      short loc_180019D38
0x180019d7f  mov     [r12], rbp
0x180019d83  mov     [r13+0], r14d
0x180019d87  jmp     loc_180019F74
0x180019d8c  mov     r8d, 1
0x180019d92  mov     edx, r14d
0x180019d95  mov     rcx, rbp
0x180019d98  jmp     loc_180019F6F
0x180019d9d  xor     ecx, ecx; pvReserved
0x180019d9f  mov     [rsp+68h+arg_0], r15d
0x180019da4  call    cs:__imp_CoInitialize
0x180019daa  mov     [rsp+68h+arg_18], r15
0x180019db2  mov     ebp, 1
0x180019db7  mov     ebx, eax
0x180019db9  cmp     eax, 80010106h
0x180019dbe  jnz     short loc_180019DC5
0x180019dc0  mov     edi, r15d
0x180019dc3  jmp     short loc_180019DD1
0x180019dc5  test    eax, eax
0x180019dc7  js      loc_180019E50
0x180019dcd  mov     edi, ebp
0x180019dcf  jnz     short loc_180019E35
0x180019dd1  lea     rax, [rsp+68h+arg_18]
0x180019dd9  mov     r8d, ebp; dwClsContext
0x180019ddc  lea     r9, IID_INetworkListManager; riid
0x180019de3  mov     [rsp+68h+ppv], rax; ppv
0x180019de8  xor     edx, edx; pUnkOuter
0x180019dea  lea     rcx, CLSID_NetworkListManager; rclsid
0x180019df1  call    cs:__imp_CoCreateInstance
0x180019df7  mov     ebx, eax
0x180019df9  test    eax, eax
0x180019dfb  jnz     short loc_180019E18
0x180019dfd  mov     rcx, [rsp+68h+arg_18]
0x180019e05  lea     rdx, [rsp+68h+arg_0]
0x180019e0a  mov     rax, [rcx]
0x180019e0d  mov     rax, [rax+68h]
0x180019e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e16  mov     ebx, eax
0x180019e18  mov     rcx, [rsp+68h+arg_18]
0x180019e20  test    rcx, rcx
0x180019e23  jz      short loc_180019E31
0x180019e25  mov     rax, [rcx]
0x180019e28  mov     rax, [rax+10h]
0x180019e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e31  test    edi, edi
0x180019e33  jz      short loc_180019E3B
0x180019e35  call    cs:__imp_CoUninitialize
0x180019e3b  test    ebx, ebx
0x180019e3d  jnz     short loc_180019E50
0x180019e3f  test    [rsp+68h+arg_0], 440h
0x180019e47  jz      short loc_180019E50
0x180019e49  xor     eax, eax
0x180019e4b  jmp     loc_180019F76
0x180019e50  mov     ebx, 40h ; '@'
0x180019e55  mov     ecx, ebx; cb
0x180019e57  call    cs:__imp_CoTaskMemAlloc
0x180019e5d  mov     rdi, rax
0x180019e60  test    rax, rax
0x180019e63  jnz     short loc_180019E6F
0x180019e65  mov     eax, 8007000Eh
0x180019e6a  jmp     loc_180019F76
0x180019e6f  mov     [rax], r15b
0x180019e72  add     rax, rbp
0x180019e75  sub     rbx, rbp
0x180019e78  jnz     short loc_180019E6F
0x180019e7a  mov     ebx, 78h ; 'x'
0x180019e7f  mov     ecx, ebx; cb
0x180019e81  call    cs:__imp_CoTaskMemAlloc
0x180019e87  mov     [rdi+30h], rax
0x180019e8b  test    rax, rax
0x180019e8e  jnz     short loc_180019E9F
0x180019e90  mov     r8d, ebp; int
0x180019e93  mov     edx, ebp; unsigned int
0x180019e95  mov     rcx, rdi; pv
0x180019e98  call    ?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z; FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)
0x180019e9d  jmp     short loc_180019E65
0x180019e9f  mov     [rax], r15b
0x180019ea2  add     rax, rbp
0x180019ea5  sub     rbx, rbp
0x180019ea8  jnz     short loc_180019E9F
0x180019eaa  mov     rsi, [rdi+30h]
0x180019eae  mov     r8, rdi; unsigned __int16 **
0x180019eb1  mov     edx, 9CC2h; unsigned int
0x180019eb6  call    ?LoadStringWithAlloc@CNetDiagClient@@IEAAJIPEAPEAGI@Z; CNetDiagClient::LoadStringWithAlloc(uint,ushort * *,uint)
0x180019ebb  mov     ebx, eax
0x180019ebd  test    eax, eax
0x180019ebf  js      loc_180019F4C
0x180019ec5  mov     r8, [rdi+30h]
0x180019ec9  mov     edx, 9CC3h; unsigned int
0x180019ece  add     r8, 18h; unsigned __int16 **
0x180019ed2  call    ?LoadStringWithAlloc@CNetDiagClient@@IEAAJIPEAPEAGI@Z; CNetDiagClient::LoadStringWithAlloc(uint,ushort * *,uint)
0x180019ed7  mov     ebx, eax
0x180019ed9  test    eax, eax
0x180019edb  js      short loc_180019F4C
0x180019edd  mov     r14, [rdi+30h]
0x180019ee1  add     r14, 10h
0x180019ee5  jz      loc_18001A00C
0x180019eeb  mov     edx, 0FFFEh
0x180019ef0  lea     rax, aPushbuttonrese; "PushButtonReset"
0x180019ef7  mov     ecx, edx
0x180019ef9  cmp     [rax], r15w
0x180019efd  jz      short loc_180019F08
0x180019eff  add     rax, 2
0x180019f03  sub     rcx, rbp
0x180019f06  jnz     short loc_180019EF9
0x180019f08  mov     rax, rcx
0x180019f0b  neg     rax
0x180019f0e  mov     rax, rcx
0x180019f11  sbb     ebx, ebx
0x180019f13  sub     rdx, rcx
0x180019f16  not     ebx
0x180019f18  and     ebx, 80070057h
0x180019f1e  neg     rax
0x180019f21  sbb     rbp, rbp
0x180019f24  and     rbp, rdx
0x180019f27  test    rcx, rcx
0x180019f2a  jz      short loc_180019F47
0x180019f2c  lea     rcx, ds:2[rbp*2]; cb
0x180019f34  call    cs:__imp_CoTaskMemAlloc
0x180019f3a  mov     [r14], rax
0x180019f3d  test    rax, rax
0x180019f40  jnz     short loc_180019F8B
0x180019f42  mov     ebx, 8007000Eh
0x180019f47  mov     ebp, 1
0x180019f4c  test    rsi, rsi
0x180019f4f  jz      short loc_180019F67
0x180019f51  xor     r8d, r8d; int
  ... truncated ...
```
