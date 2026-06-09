# CAux::HrSafeCopyElem(tagDBPROP *,tagDBPROP *,IMemoryAllocator *,ulong)

- ea: `0x180042d2c`
- end: `0x180042e5a`
- name: `?HrSafeCopyElem@CAux@@SAJPEAUtagDBPROP@@0PEAVIMemoryAllocator@@K@Z`
- size: `302`
- prototype: `__int64 __fastcall(struct tagDBPROP *, struct tagDBPROP *, struct IMemoryAllocator *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180043594`
- `0x180043a64`

## callees

- `0x180013870`
- `0x1800421a0`
- `0x18004240c`
- `0x180042d2c`
- `0x180042eb4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180042d93`
- `OLEAUT32!__imp_VariantInit` at `0x180042d93`
- `OLEAUT32!__imp_VariantClear` at `0x180042dbe`
- `OLEAUT32!__imp_VariantClear` at `0x180042dbe`
- `OLEAUT32!__imp_VariantCopy` at `0x180042da0`
- `OLEAUT32!__imp_VariantCopy` at `0x180042da0`

## string_xrefs

- `0x180042e1f`: `<CAux::HrSafeCopyElem|OLEDB|ERR> `

## pseudocode

```c
__int64 __fastcall CAux::HrSafeCopyElem(
        struct tagDBPROP *a1,
        struct tagDBPROP *a2,
        struct IMemoryAllocator *a3,
        unsigned int a4)
{
  DBID *p_colid; // rdi
  union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D uGuid; // xmm6
  __int128 v8; // xmm7
  int v11; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v13; // ebp
  int v14; // r9d
  IRecordInfo *v15; // xmm1_8
  __int64 result; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-98h] BYREF
  struct tagDBID v18; // [rsp+38h] [rbp-80h] BYREF

  p_colid = &a1->colid;
  uGuid = a1->colid.uGuid;
  v8 = *(_OWORD *)&a1->colid.eKind;
  v18.uGuid = uGuid;
  *(_OWORD *)&v18.eKind = v8;
  v11 = CAux::HrCopyDBIDs(&a1->colid, &a2->colid, a3, a4);
  if ( v11 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v11, L"<CAux::HrSafeCopyElem|OLEDB|ERR> ", 0x172u);
    p_colid->uGuid = uGuid;
    result = 2147942414LL;
    *(_OWORD *)&p_colid->eKind = v8;
    a2->dwStatus = 0;
  }
  else
  {
    pRecInfo = a1->vValue.pRecInfo;
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&a1->vValue.vt;
    pvarg.pRecInfo = pRecInfo;
    VariantInit(&a1->vValue);
    v13 = VariantCopy(&a1->vValue, &a2->vValue);
    if ( v13 )
    {
      v15 = pvarg.pRecInfo;
      *(_OWORD *)&a1->vValue.vt = *(_OWORD *)&pvarg.vt;
      a1->vValue.pRecInfo = v15;
      a2->dwStatus = 2;
    }
    else
    {
      CAux::FreeDBIDs(&v18, a3);
      VariantClear(&pvarg);
      a1->dwOptions = a2->dwOptions;
      a1->dwPropertyID = a2->dwPropertyID;
      if ( a4 )
      {
        CAux::PatchStatusFlag(a2, a1, a4, v14);
      }
      else
      {
        a1->dwStatus = a2->dwStatus;
        a2->dwStatus = 0;
      }
    }
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180042d2c  mov     rax, rsp
0x180042d2f  push    rbx
0x180042d30  push    rbp
0x180042d31  push    rsi
0x180042d32  push    rdi
0x180042d33  push    r14
0x180042d35  push    r15
0x180042d37  sub     rsp, 88h
0x180042d3e  lea     rdi, [rcx+10h]
0x180042d42  movaps  xmmword ptr [rax-48h], xmm6
0x180042d46  movups  xmm6, xmmword ptr [rdi]
0x180042d49  mov     rbx, rdx
0x180042d4c  mov     rsi, rcx
0x180042d4f  movaps  xmmword ptr [rax-58h], xmm7
0x180042d53  add     rdx, 10h; struct tagDBID *
0x180042d57  movups  xmm7, xmmword ptr [rdi+10h]
0x180042d5b  mov     rcx, rdi; struct tagDBID *
0x180042d5e  mov     r14d, r9d
0x180042d61  movups  xmmword ptr [rax-80h], xmm6
0x180042d65  mov     r15, r8
0x180042d68  movups  xmmword ptr [rax-70h], xmm7
0x180042d6c  call    ?HrCopyDBIDs@CAux@@CAJPEAUtagDBID@@PEBU2@PEAVIMemoryAllocator@@K@Z; CAux::HrCopyDBIDs(tagDBID *,tagDBID const *,IMemoryAllocator *,ulong)
0x180042d71  test    eax, eax
0x180042d73  jnz     loc_180042E10
0x180042d79  lea     rdi, [rsi+30h]
0x180042d7d  movups  xmm0, xmmword ptr [rdi]
0x180042d80  mov     rcx, rdi; pvarg
0x180042d83  movsd   xmm1, qword ptr [rdi+10h]
0x180042d88  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x180042d8d  movsd   qword ptr [rsp+0B8h+pvarg+10h], xmm1
0x180042d93  call    cs:__imp_VariantInit
0x180042d99  lea     rdx, [rbx+30h]; pvargSrc
0x180042d9d  mov     rcx, rdi; pvargDest
0x180042da0  call    cs:__imp_VariantCopy
0x180042da6  mov     ebp, eax
0x180042da8  test    eax, eax
0x180042daa  jnz     short loc_180042DF2
0x180042dac  mov     rdx, r15; struct IMemoryAllocator *
0x180042daf  lea     rcx, [rsp+0B8h+var_80]; struct tagDBID *
0x180042db4  call    ?FreeDBIDs@CAux@@CAXPEAUtagDBID@@PEAVIMemoryAllocator@@@Z; CAux::FreeDBIDs(tagDBID *,IMemoryAllocator *)
0x180042db9  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180042dbe  call    cs:__imp_VariantClear
0x180042dc4  mov     ecx, [rbx+4]
0x180042dc7  mov     [rsi+4], ecx
0x180042dca  mov     ecx, [rbx]
0x180042dcc  mov     [rsi], ecx
0x180042dce  test    r14d, r14d
0x180042dd1  jz      short loc_180042DE3
0x180042dd3  mov     r8d, r14d; unsigned int
0x180042dd6  mov     rdx, rsi; struct tagDBPROP *
0x180042dd9  mov     rcx, rbx; struct tagDBPROP *
0x180042ddc  call    ?PatchStatusFlag@CAux@@SAXPEAUtagDBPROP@@0KH@Z; CAux::PatchStatusFlag(tagDBPROP *,tagDBPROP *,ulong,int)
0x180042de1  jmp     short loc_180042E0C
0x180042de3  mov     eax, [rbx+8]
0x180042de6  mov     [rsi+8], eax
0x180042de9  mov     dword ptr [rbx+8], 0
0x180042df0  jmp     short loc_180042E0C
0x180042df2  movups  xmm0, xmmword ptr [rsp+0B8h+pvarg]
0x180042df7  movsd   xmm1, qword ptr [rsp+0B8h+pvarg+10h]
0x180042dfd  movups  xmmword ptr [rdi], xmm0
0x180042e00  movsd   qword ptr [rdi+10h], xmm1
0x180042e05  mov     dword ptr [rbx+8], 2
0x180042e0c  mov     eax, ebp
0x180042e0e  jmp     short loc_180042E40
0x180042e10  test    byte ptr cs:_bidGblFlags, 2
0x180042e17  jz      short loc_180042E2D
0x180042e19  mov     r8d, 172h; unsigned int
0x180042e1f  lea     rdx, aCauxHrsafecopy; "<CAux::HrSafeCopyElem|OLEDB|ERR> "
0x180042e26  mov     ecx, eax; int
0x180042e28  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180042e2d  movups  xmmword ptr [rdi], xmm6
0x180042e30  mov     eax, 8007000Eh
0x180042e35  movups  xmmword ptr [rdi+10h], xmm7
0x180042e39  mov     dword ptr [rbx+8], 0
0x180042e40  movaps  xmm6, [rsp+0B8h+var_48]
0x180042e45  movaps  xmm7, [rsp+0B8h+var_58]
0x180042e4a  add     rsp, 88h
0x180042e51  pop     r15
0x180042e53  pop     r14
0x180042e55  pop     rdi
0x180042e56  pop     rsi
0x180042e57  pop     rbp
0x180042e58  pop     rbx
0x180042e59  retn
```
