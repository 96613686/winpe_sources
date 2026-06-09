# UpdateBlockMap(PageBlockMap *,ulong,ulong,ulong,MemoryPage *)

- ea: `0x180041414`
- end: `0x1800415ff`
- name: `?UpdateBlockMap@@YAXPEAVPageBlockMap@@KKKPEAVMemoryPage@@@Z`
- size: `491`
- prototype: `void __fastcall(struct PageBlockMap *, unsigned int, unsigned int, unsigned int, struct MemoryPage *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028a74`

## callees

- `0x18002ca6c`
- `0x180040388`
- `0x180041414`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180041499`
- `wbemcomn!GetMemLogObject` at `0x18004150f`
- `wbemcomn!GetMemLogObject` at `0x180041561`
- `wbemcomn!GetMemLogObject` at `0x1800415a3`
- `wbemcomn!GetMemLogObject` at `0x180041499`
- `wbemcomn!GetMemLogObject` at `0x18004150f`
- `wbemcomn!GetMemLogObject` at `0x180041561`
- `wbemcomn!GetMemLogObject` at `0x1800415a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800414a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004151d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004156f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800415b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800414a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004151d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004156f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800415b1`

## pseudocode

```c
void __fastcall UpdateBlockMap(
        struct PageBlockMap *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct MemoryPage *a5)
{
  __int64 v5; // rdi
  unsigned int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r11
  CMemoryLog *v14; // rax
  CVarObjHeap *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  CMemoryLog *v18; // rax
  CVarObjHeap *v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rdx
  CMemoryLog *v22; // rax
  CMemoryLog *MemLogObject; // rax
  _BYTE v24[56]; // [rsp+30h] [rbp-38h] BYREF

  v5 = a3;
  if ( a3 >= a2 )
  {
    g_error = 1;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 1358);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = a2 - 1;
      v21 = 32;
LABEL_26:
      WPP_SF_LL(*((_QWORD *)v19 + 2), v21, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, (unsigned int)v5, v20);
    }
  }
  else
  {
    v9 = 0;
    v10 = *((_QWORD *)a5 + 2);
    while ( 1 )
    {
      if ( !*(_DWORD *)(v10 + 16LL * v9) )
      {
        g_error = 1;
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, 1358);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 31;
          goto LABEL_12;
        }
        return;
      }
      if ( *(_DWORD *)(v10 + 16LL * v9) == a4 )
        break;
      ++v9;
    }
    if ( v9 >= *((_DWORD *)a1 + 10 * a3) )
    {
      g_error = 1;
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, 1358);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = *((_DWORD *)a1 + 10 * v5);
        v21 = 30;
        goto LABEL_26;
      }
    }
    else
    {
      v11 = std::vector<bool,wbem_allocator<bool>>::operator[]((char *)a1 + 40 * a3 + 8, v24, v9);
      if ( ((1 << *(_QWORD *)(v11 + 8)) & **(_DWORD **)v11) != 0 )
      {
        g_error = 1;
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, 1358);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 29;
LABEL_12:
          WPP_SF_LL(*((_QWORD *)v15 + 2), v16, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, a4, v5);
        }
      }
      else
      {
        v17 = std::vector<bool,wbem_allocator<bool>>::operator[](v13 + 8, v24, v12);
        **(_DWORD **)v17 |= 1 << *(_QWORD *)(v17 + 8);
      }
    }
  }
}

```

## disassembly

```asm
0x180041414  push    rbx
0x180041416  push    rbp
0x180041417  push    rsi
0x180041418  push    rdi
0x180041419  push    r14
0x18004141b  sub     rsp, 40h
0x18004141f  mov     edi, r8d
0x180041422  mov     ebp, r9d
0x180041425  mov     esi, edx
0x180041427  mov     r14, rcx
0x18004142a  mov     ebx, 1
0x18004142f  cmp     r8d, edx
0x180041432  jnb     loc_18004159D
0x180041438  mov     rax, [rsp+68h+arg_20]
0x180041440  xor     edx, edx
0x180041442  mov     rcx, [rax+10h]
0x180041446  mov     eax, edx
0x180041448  add     rax, rax
0x18004144b  mov     r10d, edx
0x18004144e  cmp     dword ptr [rcx+rax*8], 0
0x180041452  jz      loc_18004155B
0x180041458  cmp     [rcx+rax*8], ebp
0x18004145b  jz      short loc_180041461
0x18004145d  add     edx, ebx
0x18004145f  jmp     short loc_180041446
0x180041461  lea     rsi, [rdi+rdi*4]
0x180041465  cmp     edx, [r14+rsi*8]
0x180041469  jnb     loc_180041509
0x18004146f  lea     r11, [r14+rsi*8]
0x180041473  mov     r8, r10
0x180041476  lea     rcx, [r11+8]
0x18004147a  lea     rdx, [rsp+68h+var_38]
0x18004147f  call    ??A?$vector@_NV?$wbem_allocator@_N@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$wbem_allocator@I@@@std@@@1@_K@Z; std::vector<bool,wbem_allocator<bool>>::operator[](unsigned __int64)
0x180041484  mov     edx, ebx
0x180041486  mov     rcx, [rax+8]
0x18004148a  mov     rax, [rax]
0x18004148d  shl     edx, cl
0x18004148f  test    [rax], edx
0x180041491  jz      short loc_1800414E8
0x180041493  mov     cs:?g_error@@3_NA, bl; bool g_error
0x180041499  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004149f  mov     rcx, rax
0x1800414a2  mov     edx, 54Eh
0x1800414a7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800414ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800414b4  lea     rax, WPP_GLOBAL_Control
0x1800414bb  cmp     rcx, rax
0x1800414be  jz      loc_1800415F4
0x1800414c4  test    [rcx+1Ch], bl
0x1800414c7  jz      loc_1800415F4
0x1800414cd  cmp     byte ptr [rcx+19h], 2
0x1800414d1  jb      loc_1800415F4
0x1800414d7  mov     edx, 1Dh
0x1800414dc  mov     [rsp+68h+var_48], edi
0x1800414e0  mov     r9d, ebp
0x1800414e3  jmp     loc_1800415E4
0x1800414e8  mov     r8, r10
0x1800414eb  lea     rdx, [rsp+68h+var_38]
0x1800414f0  lea     rcx, [r11+8]
0x1800414f4  call    ??A?$vector@_NV?$wbem_allocator@_N@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$wbem_allocator@I@@@std@@@1@_K@Z; std::vector<bool,wbem_allocator<bool>>::operator[](unsigned __int64)
0x1800414f9  mov     rcx, [rax+8]
0x1800414fd  mov     rdx, [rax]
0x180041500  shl     ebx, cl
0x180041502  or      [rdx], ebx
0x180041504  jmp     loc_1800415F4
0x180041509  mov     cs:?g_error@@3_NA, bl; bool g_error
0x18004150f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041515  mov     rcx, rax
0x180041518  mov     edx, 54Eh
0x18004151d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041523  mov     rcx, cs:WPP_GLOBAL_Control
0x18004152a  lea     rax, WPP_GLOBAL_Control
0x180041531  cmp     rcx, rax
0x180041534  jz      loc_1800415F4
0x18004153a  test    [rcx+1Ch], bl
0x18004153d  jz      loc_1800415F4
0x180041543  cmp     byte ptr [rcx+19h], 2
0x180041547  jb      loc_1800415F4
0x18004154d  mov     eax, [r14+rsi*8]
0x180041551  mov     edx, 1Eh
0x180041556  jmp     loc_1800415DD
0x18004155b  mov     cs:?g_error@@3_NA, bl; bool g_error
0x180041561  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041567  mov     rcx, rax
0x18004156a  mov     edx, 54Eh
0x18004156f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041575  mov     rcx, cs:WPP_GLOBAL_Control
0x18004157c  lea     rax, WPP_GLOBAL_Control
0x180041583  cmp     rcx, rax
0x180041586  jz      short loc_1800415F4
0x180041588  test    [rcx+1Ch], bl
0x18004158b  jz      short loc_1800415F4
0x18004158d  cmp     byte ptr [rcx+19h], 2
0x180041591  jb      short loc_1800415F4
0x180041593  mov     edx, 1Fh
0x180041598  jmp     loc_1800414DC
0x18004159d  mov     cs:?g_error@@3_NA, bl; bool g_error
0x1800415a3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800415a9  mov     rcx, rax
0x1800415ac  mov     edx, 54Eh
0x1800415b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800415b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415be  lea     rax, WPP_GLOBAL_Control
0x1800415c5  cmp     rcx, rax
0x1800415c8  jz      short loc_1800415F4
0x1800415ca  test    [rcx+1Ch], bl
0x1800415cd  jz      short loc_1800415F4
0x1800415cf  cmp     byte ptr [rcx+19h], 2
0x1800415d3  jb      short loc_1800415F4
0x1800415d5  lea     eax, [rsi-1]
0x1800415d8  mov     edx, 20h ; ' '
0x1800415dd  mov     r9d, edi
0x1800415e0  mov     [rsp+68h+var_48], eax
0x1800415e4  mov     rcx, [rcx+10h]
0x1800415e8  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x1800415ef  call    WPP_SF_LL
0x1800415f4  add     rsp, 40h
0x1800415f8  pop     r14
0x1800415fa  pop     rdi
0x1800415fb  pop     rsi
0x1800415fc  pop     rbp
0x1800415fd  pop     rbx
0x1800415fe  retn
```
