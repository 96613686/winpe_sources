# CStagingPoolBase::CreateStagingPool(CDDPDEV *,uint,uint,uint,_DXGKCDD_CREATE_ALLOCATION_FLAGS)

- ea: `0x14002fa88`
- end: `0x14002fbcb`
- name: `?CreateStagingPool@CStagingPoolBase@@QEAAJPEAUCDDPDEV@@IIIU_DXGKCDD_CREATE_ALLOCATION_FLAGS@@@Z`
- size: `323`
- prototype: `int __high(struct CDDPDEV *, unsigned int, unsigned int, unsigned int, struct _DXGKCDD_CREATE_ALLOCATION_FLAGS)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001d980`

## callees

- `0x140015ce0`
- `0x14001bff8`
- `0x14002fa88`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002fb6b`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002fb6b`
- `watchdog!WdLogSingleEntry0` at `0x14002fb54`
- `watchdog!WdLogSingleEntry0` at `0x14002fb54`

## pseudocode

```c
__int64 __fastcall CStagingPoolBase::CreateStagingPool(
        __int64 a1,
        struct CDDPDEV *a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6)
{
  unsigned int v6; // esi
  CddBitmapBase *v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 result; // rax

  v6 = 0;
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 48) = a5;
  while ( v6 < a5 )
  {
    v11 = (CddBitmapBase *)operator new(0xD8u);
    if ( v11 )
    {
      CddBitmapBase::CddBitmapBase(v11, a2);
      *(_QWORD *)(v12 + 128) = 0;
      *(_QWORD *)v12 = &CddBitmapStagingApertureMem::`vftable';
      *(_QWORD *)(v12 + 136) = 0;
      *(_DWORD *)(v12 + 144) = 0;
      *(_DWORD *)(v12 + 168) = 0;
      *(_DWORD *)(v12 + 172) = a6;
      *(_QWORD *)(v12 + 176) = 0;
      *(_QWORD *)(v12 + 184) = 0;
      *(_DWORD *)(v12 + 192) = 0;
      *(_BYTE *)(v12 + 196) = 0;
      *(_DWORD *)(v12 + 200) = 0;
      *(_QWORD *)(v12 + 208) = a1;
    }
    else
    {
      v12 = 0;
    }
    *(_QWORD *)(a1 + 8LL * v6 + 64) = v12;
    if ( !v12 )
    {
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 72;
      v13 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      v13[3] = gCddImageInfo;
      v13[4] = (unsigned int)dword_14003E570;
      v13[5] = 215857758;
      result = 3221225473LL;
      WdLogGlobalForLineNumber = 72;
      return result;
    }
    ++v6;
  }
  *(_QWORD *)(a1 + 32) = 0;
  result = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 12) = a3;
  *(_DWORD *)(a1 + 16) = a4;
  *(_DWORD *)(a1 + 128) = a6;
  return result;
}

```

## disassembly

```asm
0x14002fa88  push    rbx
0x14002fa8a  push    rbp
0x14002fa8b  push    rsi
0x14002fa8c  push    rdi
0x14002fa8d  push    r12
0x14002fa8f  push    r13
0x14002fa91  push    r14
0x14002fa93  push    r15
0x14002fa95  sub     rsp, 28h
0x14002fa99  mov     ebp, [rsp+68h+arg_20]
0x14002faa0  xor     r13d, r13d
0x14002faa3  mov     ebx, [rsp+68h+arg_28]
0x14002faaa  mov     esi, r13d
0x14002faad  mov     r14d, r9d
0x14002fab0  mov     [rcx], rdx
0x14002fab3  mov     r15d, r8d
0x14002fab6  mov     [rcx+30h], ebp
0x14002fab9  mov     r12, rdx
0x14002fabc  mov     rdi, rcx
0x14002fabf  cmp     esi, ebp
0x14002fac1  jnb     loc_14002FBA1
0x14002fac7  mov     ecx, 0D8h; cjMemSize
0x14002facc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002fad1  mov     rcx, rax; this
0x14002fad4  test    rax, rax
0x14002fad7  jz      short loc_14002FB39
0x14002fad9  mov     rdx, r12; struct CDDPDEV *
0x14002fadc  call    ??0CddBitmapBase@@QEAA@PEAUCDDPDEV@@@Z; CddBitmapBase::CddBitmapBase(CDDPDEV *)
0x14002fae1  lea     r9, ??_7CddBitmapStagingApertureMem@@6B@; const CddBitmapStagingApertureMem::`vftable'
0x14002fae8  mov     [rcx+80h], r13
0x14002faef  mov     [rcx], r9
0x14002faf2  mov     [rcx+88h], r13
0x14002faf9  mov     [rcx+90h], r13d
0x14002fb00  mov     [rcx+0A8h], r13d
0x14002fb07  mov     [rcx+0ACh], ebx
0x14002fb0d  mov     [rcx+0B0h], r13
0x14002fb14  mov     [rcx+0B8h], r13
0x14002fb1b  mov     [rcx+0C0h], r13d
0x14002fb22  mov     [rcx+0C4h], r13b
0x14002fb29  mov     [rcx+0C8h], r13d
0x14002fb30  mov     [rcx+0D0h], rdi
0x14002fb37  jmp     short loc_14002FB3C
0x14002fb39  mov     rcx, r13
0x14002fb3c  mov     eax, esi
0x14002fb3e  mov     [rdi+rax*8+40h], rcx
0x14002fb43  test    rcx, rcx
0x14002fb46  jz      short loc_14002FB4F
0x14002fb48  inc     esi
0x14002fb4a  jmp     loc_14002FABF
0x14002fb4f  mov     ecx, 6
0x14002fb54  call    cs:__imp_WdLogSingleEntry0
0x14002fb5b  nop     dword ptr [rax+rax+00h]
0x14002fb60  mov     ebx, 48h ; 'H'
0x14002fb65  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002fb6b  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002fb72  nop     dword ptr [rax+rax+00h]
0x14002fb77  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002fb7e  mov     [rax+18h], rcx
0x14002fb82  mov     ecx, cs:dword_14003E570
0x14002fb88  mov     [rax+20h], rcx
0x14002fb8c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002fb94  mov     eax, 0C0000001h
0x14002fb99  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002fb9f  jmp     short loc_14002FBB9
0x14002fba1  mov     [rdi+20h], r13
0x14002fba5  xor     eax, eax
0x14002fba7  mov     [rdi+28h], r13
0x14002fbab  mov     [rdi+0Ch], r15d
0x14002fbaf  mov     [rdi+10h], r14d
0x14002fbb3  mov     [rdi+80h], ebx
0x14002fbb9  add     rsp, 28h
0x14002fbbd  pop     r15
0x14002fbbf  pop     r14
0x14002fbc1  pop     r13
0x14002fbc3  pop     r12
0x14002fbc5  pop     rdi
0x14002fbc6  pop     rsi
0x14002fbc7  pop     rbp
0x14002fbc8  pop     rbx
0x14002fbc9  retn
```
