# CUtlProps::SetProperty(ulong,ulong,tagDBPROP *,int)

- ea: `0x18002cc98`
- end: `0x18002ced7`
- name: `?SetProperty@CUtlProps@@AEAAXKKPEAUtagDBPROP@@H@Z`
- size: `575`
- prototype: `void(CUtlProps *__hidden this, unsigned int, unsigned int, struct tagDBPROP *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002d030`

## callees

- `0x180001dd4`
- `0x1800028b8`
- `0x18001b008`
- `0x18002ae2c`
- `0x18002aee0`
- `0x18002b17c`
- `0x18002cc98`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002cddc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002ce81`
- `OLEAUT32!__imp_VariantCopy` at `0x18002cddc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002ce81`

## pseudocode

```c
void __fastcall CUtlProps::SetProperty(CUtlProps *this, unsigned int a2, unsigned int a3, struct tagDBPROP *a4)
{
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v8; // rbp
  unsigned int v9; // r10d
  __int64 v10; // r11
  unsigned int v11; // r9d
  __int64 v12; // rdx
  const struct tagDBID *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  int v16; // eax
  CColumnIds *v17; // rcx
  unsigned int v18; // edx
  CColumnIds *v19; // rcx
  HRESULT v20; // eax
  int v21; // ebx
  unsigned __int8 *v22; // rax
  HRESULT v23; // eax
  int v24; // ebx

  v4 = *((_QWORD *)this + 3);
  v5 = a2;
  *((_DWORD *)this + 20) = 1;
  v8 = a3;
  v9 = 0;
  v10 = 3LL * a2;
  v11 = *(_DWORD *)(v4 + 24LL * a2);
  if ( v11 )
  {
    v12 = *(_QWORD *)(v4 + 24LL * a2 + 8);
    while ( **(_DWORD **)(v12 + 8LL * v9) != a4->dwPropertyID )
    {
      if ( ++v9 >= v11 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    if ( v9 >= v11 )
    {
      a4->dwStatus = 1;
      ThrowHR(-2147467259);
    }
  }
  v13 = (const struct tagDBID *)(5 * v5);
  v14 = *(_QWORD *)(*((_QWORD *)this + 2) + 40 * v5 + 16);
  v15 = 48LL * v9 + *(_QWORD *)(v4 + 8 * v10 + 16);
  *(_DWORD *)(v15 + 40) = (a4->dwOptions != 0) + 1;
  v16 = *(_DWORD *)(v14 + 24 * v8 + 8) & 0x100;
  if ( a4->vValue.vt )
  {
    if ( v16 )
    {
      if ( CompareDBIDs(&a4->colid, v13) == 1 )
      {
        v19 = *(CColumnIds **)(v15 + 8);
        if ( v19 )
          CColumnIds::`scalar deleting destructor'(v19, v18);
        *(_QWORD *)(v15 + 8) = 0;
        *(_DWORD *)v15 = a4->dwOptions;
        v20 = VariantCopy((VARIANTARG *)(v15 + 16), &a4->vValue);
        v21 = v20;
        if ( v20 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049EB0[0] )
            bidTraceW(off_180049220, 2257920, off_180049EB0[0], (unsigned int)v20, 2205);
          ThrowHR(v21);
        }
      }
      else
      {
        if ( !*(_QWORD *)(v15 + 8) )
        {
          v22 = MMMAlloc(0x18u, v18);
          if ( v22 )
          {
            *(_QWORD *)v22 = 0;
            *((_QWORD *)v22 + 1) = 0;
            *((_DWORD *)v22 + 4) = 0;
          }
          else
          {
            v22 = 0;
          }
          *(_QWORD *)(v15 + 8) = v22;
          OnNullThrowOOM(v22);
        }
        CColumnIds::AddColumnId(*(CColumnIds **)(v15 + 8), a4);
      }
    }
    else
    {
      *(_DWORD *)v15 = a4->dwOptions;
      v23 = VariantCopy((VARIANTARG *)(v15 + 16), &a4->vValue);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049EB8[0] )
          bidTraceW(off_180049220, 2276352, off_180049EB8[0], (unsigned int)v23, 2223);
        ThrowHR(v24);
      }
    }
  }
  else
  {
    if ( v16 )
    {
      v17 = *(CColumnIds **)(v15 + 8);
      if ( v17 )
        CColumnIds::`scalar deleting destructor'(v17, (unsigned int)v13);
      *(_QWORD *)(v15 + 8) = 0;
    }
    (*(void (__fastcall **)(CUtlProps *, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)this + 40LL))(
      this,
      (unsigned int)v5,
      a4->dwPropertyID,
      v15,
      v15 + 16);
  }
}

```

## disassembly

```asm
0x18002cc98  mov     [rsp+arg_8], rbx
0x18002cc9d  mov     [rsp+arg_10], rbp
0x18002cca2  push    rsi
0x18002cca3  push    rdi
0x18002cca4  push    r12
0x18002cca6  push    r14
0x18002cca8  push    r15
0x18002ccaa  sub     rsp, 30h
0x18002ccae  mov     rbx, [rcx+18h]
0x18002ccb2  xor     r12d, r12d
0x18002ccb5  mov     r15d, edx
0x18002ccb8  mov     rdi, r9
0x18002ccbb  mov     dword ptr [rcx+50h], 1
0x18002ccc2  mov     rsi, rcx
0x18002ccc5  mov     ebp, r8d
0x18002ccc8  mov     r10d, r12d
0x18002cccb  lea     r11, [r15+r15*2]
0x18002cccf  mov     r9d, [rbx+r11*8]
0x18002ccd3  test    r9d, r9d
0x18002ccd6  jz      short loc_18002CCF4
0x18002ccd8  mov     rdx, [rbx+r11*8+8]
0x18002ccdd  mov     r8d, [rdi]
0x18002cce0  mov     eax, r10d
0x18002cce3  mov     rcx, [rdx+rax*8]
0x18002cce7  cmp     [rcx], r8d
0x18002ccea  jz      short loc_18002CD0B
0x18002ccec  inc     r10d
0x18002ccef  cmp     r10d, r9d
0x18002ccf2  jb      short loc_18002CCE0
0x18002ccf4  cmp     r10d, r9d
0x18002ccf7  jb      short loc_18002CD0B
0x18002ccf9  mov     ecx, 80004005h; int
0x18002ccfe  mov     dword ptr [rdi+8], 1
0x18002cd05  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002cd0b  mov     rcx, [rsi+10h]
0x18002cd0f  lea     r9, ds:0[rbp*2]
0x18002cd17  mov     rbx, [rbx+r11*8+10h]
0x18002cd1c  lea     rdx, [r15+r15*4]; struct tagDBID *
0x18002cd20  add     r9, rbp
0x18002cd23  mov     eax, r10d
0x18002cd26  lea     rbp, [rdi+30h]
0x18002cd2a  mov     r8, [rcx+rdx*8+10h]
0x18002cd2f  lea     rcx, [rax+rax*2]
0x18002cd33  mov     eax, [rdi+4]
0x18002cd36  shl     rcx, 4
0x18002cd3a  add     rbx, rcx
0x18002cd3d  neg     eax
0x18002cd3f  sbb     ecx, ecx
0x18002cd41  neg     ecx
0x18002cd43  inc     ecx
0x18002cd45  mov     [rbx+28h], ecx
0x18002cd48  mov     eax, [r8+r9*8+8]
0x18002cd4d  and     eax, 100h
0x18002cd52  cmp     [rbp+0], r12w
0x18002cd57  jnz     short loc_18002CDA8
0x18002cd59  test    eax, eax
0x18002cd5b  jz      short loc_18002CD6F
0x18002cd5d  mov     rcx, [rbx+8]; this
0x18002cd61  test    rcx, rcx
0x18002cd64  jz      short loc_18002CD6B
0x18002cd66  call    ??_GCColumnIds@@QEAAPEAXI@Z; CColumnIds::`scalar deleting destructor'(uint)
0x18002cd6b  mov     [rbx+8], r12
0x18002cd6f  mov     rax, [rsi]
0x18002cd72  lea     rcx, [rbx+10h]
0x18002cd76  mov     r8d, [rdi]
0x18002cd79  mov     r9, rbx
0x18002cd7c  mov     [rsp+58h+var_38], rcx
0x18002cd81  mov     edx, r15d
0x18002cd84  mov     rcx, rsi
0x18002cd87  mov     rax, [rax+28h]
0x18002cd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd90  mov     rbx, [rsp+58h+arg_8]
0x18002cd95  mov     rbp, [rsp+58h+arg_10]
0x18002cd9a  add     rsp, 30h
0x18002cd9e  pop     r15
0x18002cda0  pop     r14
0x18002cda2  pop     r12
0x18002cda4  pop     rdi
0x18002cda5  pop     rsi
0x18002cda6  retn
0x18002cda8  test    eax, eax
0x18002cdaa  jz      loc_18002CE75
0x18002cdb0  lea     rcx, [rdi+10h]; struct tagDBID *
0x18002cdb4  call    ?CompareDBIDs@@YAKPEBUtagDBID@@0@Z; CompareDBIDs(tagDBID const *,tagDBID const *)
0x18002cdb9  cmp     eax, 1
0x18002cdbc  jnz     short loc_18002CE2E
0x18002cdbe  mov     rcx, [rbx+8]; this
0x18002cdc2  test    rcx, rcx
0x18002cdc5  jz      short loc_18002CDCC
0x18002cdc7  call    ??_GCColumnIds@@QEAAPEAXI@Z; CColumnIds::`scalar deleting destructor'(uint)
0x18002cdcc  mov     [rbx+8], r12
0x18002cdd0  lea     rcx, [rbx+10h]; pvargDest
0x18002cdd4  mov     eax, [rdi+4]
0x18002cdd7  mov     rdx, rbp; pvargSrc
0x18002cdda  mov     [rbx], eax
0x18002cddc  call    cs:__imp_VariantCopy
0x18002cde3  nop     dword ptr [rax+rax+00h]
0x18002cde8  mov     ebx, eax
0x18002cdea  test    eax, eax
0x18002cdec  jns     short loc_18002CD90
0x18002cdee  test    byte ptr cs:_bidGblFlags, 2
0x18002cdf5  jz      short loc_18002CE26
0x18002cdf7  mov     rcx, cs:off_180049EB0; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002cdfe  test    rcx, rcx
0x18002ce01  jz      short loc_18002CE26
0x18002ce03  mov     r8, cs:off_180049EB0; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002ce0a  mov     r9d, eax
0x18002ce0d  mov     rcx, cs:off_180049220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002ce14  mov     edx, 227400h
0x18002ce19  mov     dword ptr [rsp+58h+var_38], 89Dh
0x18002ce21  call    _bidTraceW
0x18002ce26  mov     ecx, ebx; int
0x18002ce28  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002ce2e  cmp     [rbx+8], r12
0x18002ce32  jnz     short loc_18002CE64
0x18002ce34  mov     ecx, 18h; unsigned int
0x18002ce39  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002ce3e  mov     [rsp+58h+arg_0], rax
0x18002ce43  test    rax, rax
0x18002ce46  jz      short loc_18002CE55
0x18002ce48  mov     [rax], r12
0x18002ce4b  mov     [rax+8], r12
0x18002ce4f  mov     [rax+10h], r12d
0x18002ce53  jmp     short loc_18002CE58
0x18002ce55  mov     rax, r12
0x18002ce58  mov     rcx, rax; void *
0x18002ce5b  mov     [rbx+8], rax
0x18002ce5f  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002ce64  mov     rcx, [rbx+8]; this
0x18002ce68  mov     rdx, rdi; struct tagDBPROP *
0x18002ce6b  call    ?AddColumnId@CColumnIds@@QEAAXPEAUtagDBPROP@@@Z; CColumnIds::AddColumnId(tagDBPROP *)
0x18002ce70  jmp     loc_18002CD90
0x18002ce75  mov     eax, [rdi+4]
0x18002ce78  lea     rcx, [rbx+10h]; pvargDest
0x18002ce7c  mov     rdx, rbp; pvargSrc
0x18002ce7f  mov     [rbx], eax
0x18002ce81  call    cs:__imp_VariantCopy
0x18002ce88  nop     dword ptr [rax+rax+00h]
0x18002ce8d  mov     ebx, eax
0x18002ce8f  test    eax, eax
0x18002ce91  jns     loc_18002CD90
0x18002ce97  test    byte ptr cs:_bidGblFlags, 2
0x18002ce9e  jz      short loc_18002CECF
0x18002cea0  mov     rcx, cs:off_180049EB8; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002cea7  test    rcx, rcx
0x18002ceaa  jz      short loc_18002CECF
0x18002ceac  mov     r8, cs:off_180049EB8; "<CUtlProps::SetProperty|ADO|ERR>  HRESU"...
0x18002ceb3  mov     r9d, eax
0x18002ceb6  mov     rcx, cs:off_180049220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002cebd  mov     edx, 22BC00h
0x18002cec2  mov     dword ptr [rsp+58h+var_38], 8AFh
0x18002ceca  call    _bidTraceW
0x18002cecf  mov     ecx, ebx; int
0x18002ced1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
