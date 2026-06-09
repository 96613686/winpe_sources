# CPageCache::Flush(void)

- ea: `0x18001abc0`
- end: `0x18001ad52`
- name: `?Flush@CPageCache@@QEAAKXZ`
- size: `402`
- prototype: `DWORD __fastcall(CPageCache *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001aed0`
- `0x180039560`

## callees

- `0x1800012b8`
- `0x18000f460`
- `0x18000f8a0`
- `0x18000f950`
- `0x180011490`
- `0x18001a56c`
- `0x18001abc0`
- `0x18001ad58`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001ac99`
- `wbemcomn!GetMemLogObject` at `0x18001ac99`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001aca4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001aca4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001abdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ad20`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001abdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ad20`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001ad0e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001ad0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad18`

## pseudocode

```c
DWORD __fastcall CPageCache::Flush(CPageCache *this)
{
  DWORD TickCount; // eax
  SCachePage **v3; // r14
  __int64 v4; // rsi
  unsigned int i; // ebp
  SCachePage *v6; // rax
  unsigned int v7; // r15d
  unsigned __int8 **v8; // rdi
  unsigned int v9; // r12d
  unsigned int v10; // edi
  __int64 v11; // r9
  CMemoryLog *MemLogObject; // rax
  _DWORD v14[2]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 **v15; // [rsp+38h] [rbp-30h]
  __int64 v16; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 8) )
  {
    v3 = (SCachePage **)((char *)this + 88);
    v4 = (__int64)(*((_QWORD *)this + 12) - *((_QWORD *)this + 11)) >> 4;
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      v6 = *v3;
      v7 = *((_DWORD *)*v3 + 4 * i);
      v14[0] = v7;
      v8 = (unsigned __int8 **)*((_QWORD *)v6 + 2 * i + 1);
      v15 = v8;
      v9 = *((_DWORD *)v6 + 4 * i + 1);
      v14[1] = v9;
      if ( v8 )
        MemoryPage::AddRef((MemoryPage *)v8);
      v10 = CPageCache::WritePhysPage(this, v7, v8[2], v9);
      if ( v10 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v10);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v10);
        }
        SCachePage::~SCachePage((SCachePage *)v14);
        return v10;
      }
      std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(
        (__int64 *)this + 8,
        &v16,
        *((_QWORD *)this + 8),
        v11,
        (struct SCachePage *)v14);
      if ( (__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 4 > (unsigned __int64)*((unsigned int *)this + 2) )
        std::vector<SCachePage,wbem_allocator<SCachePage>>::pop_back((char *)this + 64);
      SCachePage::~SCachePage((SCachePage *)v14);
    }
    std::vector<SCachePage,wbem_allocator<SCachePage>>::clear(v3);
    if ( g_bShuttingDown && g_ShutDownFlags == 1 )
      return 0;
    if ( !FlushFileBuffers(*((HANDLE *)this + 7)) )
      return GetLastError();
    TickCount = GetTickCount();
    *((_DWORD *)this + 30) = 0;
  }
  else
  {
    TickCount = GetTickCount();
  }
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 7) = TickCount;
  return 0;
}

```

## disassembly

```asm
0x18001abc0  mov     [rsp+arg_8], rbx
0x18001abc5  mov     [rsp+arg_10], rbp
0x18001abca  push    rsi
0x18001abcb  push    rdi
0x18001abcc  push    r12
0x18001abce  push    r14
0x18001abd0  push    r15
0x18001abd2  sub     rsp, 40h
0x18001abd6  mov     rbx, rcx
0x18001abd9  cmp     dword ptr [rcx+20h], 0
0x18001abdd  jnz     short loc_18001ABEA
0x18001abdf  call    cs:__imp_GetTickCount
0x18001abe5  jmp     loc_18001AD2D
0x18001abea  lea     r14, [rcx+58h]
0x18001abee  mov     rsi, [r14+8]
0x18001abf2  sub     rsi, [r14]
0x18001abf5  sar     rsi, 4
0x18001abf9  xor     ebp, ebp
0x18001abfb  cmp     ebp, esi
0x18001abfd  jnb     loc_18001ACF0
0x18001ac03  mov     ecx, ebp
0x18001ac05  add     rcx, rcx
0x18001ac08  mov     rax, [r14]
0x18001ac0b  mov     r15d, [rax+rcx*8]
0x18001ac0f  mov     [rsp+68h+var_38], r15d
0x18001ac14  mov     rdi, [rax+rcx*8+8]
0x18001ac19  mov     [rsp+68h+var_30], rdi
0x18001ac1e  mov     r12d, [rax+rcx*8+4]
0x18001ac23  mov     [rsp+68h+var_34], r12d
0x18001ac28  test    rdi, rdi
0x18001ac2b  jz      short loc_18001AC36
0x18001ac2d  mov     rcx, rdi; this
0x18001ac30  call    ?AddRef@MemoryPage@@QEAAJXZ; MemoryPage::AddRef(void)
0x18001ac35  nop
0x18001ac36  mov     r9d, r12d; unsigned int
0x18001ac39  mov     r8, [rdi+10h]; unsigned __int8 *
0x18001ac3d  mov     edx, r15d; unsigned int
0x18001ac40  mov     rcx, rbx; this
0x18001ac43  call    ?WritePhysPage@CPageCache@@QEAAKKPEAEK@Z; CPageCache::WritePhysPage(ulong,uchar *,ulong)
0x18001ac48  mov     edi, eax
0x18001ac4a  test    eax, eax
0x18001ac4c  jnz     short loc_18001AC99
0x18001ac4e  lea     rdi, [rbx+40h]
0x18001ac52  lea     rax, [rsp+68h+var_38]
0x18001ac57  mov     [rsp+68h+var_48], rax; struct SCachePage *
0x18001ac5c  mov     r8, [rdi]; int
0x18001ac5f  lea     rdx, [rsp+68h+arg_0]; int
0x18001ac64  mov     rcx, rdi; int
0x18001ac67  call    ?_Insert_n@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@_KAEBUSCachePage@@@Z; std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SCachePage>>>,unsigned __int64,SCachePage const &)
0x18001ac6c  mov     rdx, [rdi+8]
0x18001ac70  sub     rdx, [rdi]
0x18001ac73  sar     rdx, 4
0x18001ac77  mov     eax, [rbx+8]
0x18001ac7a  cmp     rdx, rax
0x18001ac7d  jbe     short loc_18001AC88
0x18001ac7f  mov     rcx, rdi
0x18001ac82  call    ?pop_back@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@QEAAXXZ; std::vector<SCachePage,wbem_allocator<SCachePage>>::pop_back(void)
0x18001ac87  nop
0x18001ac88  lea     rcx, [rsp+68h+var_38]; this
0x18001ac8d  call    ??1SCachePage@@QEAA@XZ; SCachePage::~SCachePage(void)
0x18001ac92  inc     ebp
0x18001ac94  jmp     loc_18001ABFB
0x18001ac99  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001ac9f  mov     edx, edi
0x18001aca1  mov     rcx, rax
0x18001aca4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001acaa  lea     rax, WPP_GLOBAL_Control
0x18001acb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acb8  cmp     rcx, rax
0x18001acbb  jz      short loc_18001ACE2
0x18001acbd  test    byte ptr [rcx+1Ch], 1
0x18001acc1  jz      short loc_18001ACE2
0x18001acc3  cmp     byte ptr [rcx+19h], 2
0x18001acc7  jb      short loc_18001ACE2
0x18001acc9  mov     edx, 25h ; '%'
0x18001acce  mov     r9d, edi
0x18001acd1  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001acd8  mov     rcx, [rcx+10h]
0x18001acdc  call    WPP_SF_d
0x18001ace1  nop
0x18001ace2  lea     rcx, [rsp+68h+var_38]; this
0x18001ace7  call    ??1SCachePage@@QEAA@XZ; SCachePage::~SCachePage(void)
0x18001acec  mov     eax, edi
0x18001acee  jmp     short loc_18001AD39
0x18001acf0  mov     rcx, r14
0x18001acf3  call    ?clear@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@QEAAXXZ; std::vector<SCachePage,wbem_allocator<SCachePage>>::clear(void)
0x18001acf8  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x18001acff  jz      short loc_18001AD0A
0x18001ad01  cmp     cs:?g_ShutDownFlags@@3KA, 1; ulong g_ShutDownFlags
0x18001ad08  jz      short loc_18001AD37
0x18001ad0a  mov     rcx, [rbx+38h]; hFile
0x18001ad0e  call    cs:__imp_FlushFileBuffers
0x18001ad14  test    eax, eax
0x18001ad16  jnz     short loc_18001AD20
0x18001ad18  call    cs:__imp_GetLastError
0x18001ad1e  jmp     short loc_18001AD39
0x18001ad20  call    cs:__imp_GetTickCount
0x18001ad26  mov     dword ptr [rbx+78h], 0
0x18001ad2d  mov     dword ptr [rbx+20h], 0
0x18001ad34  mov     [rbx+1Ch], eax
0x18001ad37  xor     eax, eax
0x18001ad39  lea     r11, [rsp+68h+var_28]
0x18001ad3e  mov     rbx, [r11+38h]
0x18001ad42  mov     rbp, [r11+40h]
0x18001ad46  mov     rsp, r11
0x18001ad49  pop     r15
0x18001ad4b  pop     r14
0x18001ad4d  pop     r12
0x18001ad4f  pop     rdi
0x18001ad50  pop     rsi
0x18001ad51  retn
```
