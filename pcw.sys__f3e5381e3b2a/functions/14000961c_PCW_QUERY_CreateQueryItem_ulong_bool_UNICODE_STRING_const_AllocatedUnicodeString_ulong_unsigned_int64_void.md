# PCW_QUERY::CreateQueryItem(ulong *,bool,_UNICODE_STRING const *,AllocatedUnicodeString &&,ulong,unsigned __int64,void *)

- ea: `0x14000961c`
- end: `0x140009749`
- name: `?CreateQueryItem@PCW_QUERY@@QEAAJPEAK_NPEBU_UNICODE_STRING@@$$QEAVAllocatedUnicodeString@@K_KPEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140009d40`

## callees

- `0x140008140`
- `0x1400090d8`
- `0x14000961c`
- `0x140009750`
- `0x14000d660`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400096a3`
- `ntoskrnl!ExAllocatePool2` at `0x1400096a3`

## pseudocode

```c
__int64 __fastcall PCW_QUERY::CreateQueryItem(
        __int64 a1,
        __int64 a2,
        char a3,
        const struct _UNICODE_STRING *a4,
        __int64 a5,
        int a6,
        char a7,
        __int64 a8)
{
  __int64 v12; // rcx
  int v13; // edi
  __int64 Pool2; // rax
  __int64 v15; // rcx
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19[7]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 48)) <= 0xFFFF )
  {
    v20 = 0;
    v13 = PCW_COUNTERSET::FindOrCreate(&v20, a4, 1u);
    if ( v13 >= 0 )
    {
      Pool2 = ExAllocatePool2(257, 104, 1366778704);
      if ( Pool2
        && (LOBYTE(v16) = a3,
            (v17 = PCW_QUERY_ITEM::PCW_QUERY_ITEM(Pool2, (unsigned int)&v20, a5, v16, a6, (__int64)&a7, a8)) != 0) )
      {
        v19[0] = v17;
        PCW_QUERY::InsertQueryItem(a1, v19, a2);
        if ( v20 )
          ReleaseDeleter<PCW_COUNTERSET>::operator()(v18, v20);
        return 0;
      }
      else
      {
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
        if ( v20 )
          ReleaseDeleter<PCW_COUNTERSET>::operator()(v15, v20);
        return 3221225495LL;
      }
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
      if ( v20 )
        ReleaseDeleter<PCW_COUNTERSET>::operator()(v12, v20);
      return (unsigned int)v13;
    }
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000961c  push    rbx
0x14000961e  push    rbp
0x14000961f  push    rsi
0x140009620  push    rdi
0x140009621  sub     rsp, 58h
0x140009625  mov     bpl, r8b
0x140009628  mov     rsi, rdx
0x14000962b  mov     r8d, 1
0x140009631  mov     rbx, rcx
0x140009634  mov     eax, r8d
0x140009637  lock xadd [rcx+30h], eax
0x14000963c  add     eax, r8d
0x14000963f  cmp     eax, 0FFFFh
0x140009644  jle     short loc_140009654
0x140009646  lock dec dword ptr [rcx+30h]
0x14000964a  mov     eax, 0C000009Ah
0x14000964f  jmp     loc_14000973F
0x140009654  mov     rdx, r9
0x140009657  mov     [rsp+78h+arg_0], 0
0x140009663  lea     rcx, [rsp+78h+arg_0]
0x14000966b  call    ?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@K@Z; PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *,ulong)
0x140009670  mov     edi, eax
0x140009672  test    eax, eax
0x140009674  jns     short loc_140009693
0x140009676  lock dec dword ptr [rbx+30h]
0x14000967a  mov     rdx, [rsp+78h+arg_0]
0x140009682  test    rdx, rdx
0x140009685  jz      short loc_14000968C
0x140009687  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000968c  mov     eax, edi
0x14000968e  jmp     loc_14000973F
0x140009693  mov     edx, 68h ; 'h'
0x140009698  mov     ecx, 101h
0x14000969d  mov     r8d, 51776350h
0x1400096a3  call    cs:__imp_ExAllocatePool2
0x1400096aa  nop     dword ptr [rax+rax+00h]
0x1400096af  test    rax, rax
0x1400096b2  jz      short loc_140009724
0x1400096b4  mov     rcx, [rsp+78h+arg_38]
0x1400096bc  lea     rdx, [rsp+78h+arg_0]
0x1400096c4  mov     r8, [rsp+78h+arg_20]
0x1400096cc  mov     r9b, bpl
0x1400096cf  mov     [rsp+78h+var_48], rcx
0x1400096d4  lea     rcx, [rsp+78h+arg_30]
0x1400096dc  mov     [rsp+78h+var_50], rcx
0x1400096e1  mov     ecx, [rsp+78h+arg_28]
0x1400096e8  mov     [rsp+78h+var_58], ecx
0x1400096ec  mov     rcx, rax
0x1400096ef  call    ??0PCW_QUERY_ITEM@@QEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@$$QEAVAllocatedUnicodeString@@_NKAEB_KPEAX@Z; PCW_QUERY_ITEM::PCW_QUERY_ITEM(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,AllocatedUnicodeString &&,bool,ulong,unsigned __int64 const &,void *)
0x1400096f4  test    rax, rax
0x1400096f7  jz      short loc_140009724
0x1400096f9  mov     r8, rsi
0x1400096fc  mov     [rsp+78h+var_38], rax
0x140009701  lea     rdx, [rsp+78h+var_38]
0x140009706  mov     rcx, rbx
0x140009709  call    ?InsertQueryItem@PCW_QUERY@@AEAAXV?$unique_ptr@VPCW_QUERY_ITEM@@U?$default_delete@VPCW_QUERY_ITEM@@@utl@@@utl@@PEAK@Z; PCW_QUERY::InsertQueryItem(utl::unique_ptr<PCW_QUERY_ITEM,utl::default_delete<PCW_QUERY_ITEM>>,ulong *)
0x14000970e  mov     rdx, [rsp+78h+arg_0]
0x140009716  test    rdx, rdx
0x140009719  jz      short loc_140009720
0x14000971b  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x140009720  xor     eax, eax
0x140009722  jmp     short loc_14000973F
0x140009724  lock dec dword ptr [rbx+30h]
0x140009728  mov     rdx, [rsp+78h+arg_0]
0x140009730  test    rdx, rdx
0x140009733  jz      short loc_14000973A
0x140009735  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000973a  mov     eax, 0C0000017h
0x14000973f  add     rsp, 58h
0x140009743  pop     rdi
0x140009744  pop     rsi
0x140009745  pop     rbp
0x140009746  pop     rbx
0x140009747  retn
```
