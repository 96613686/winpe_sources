# MDnsGetLocalAandAAAARecords(_DnsNetInfo *,ushort const *,ulong,ushort,ulong,_DnsRecordW * *)

- ea: `0x18000f390`
- end: `0x18000f7a5`
- name: `?MDnsGetLocalAandAAAARecords@@YAJPEAU_DnsNetInfo@@PEBGKGKPEAPEAU_DnsRecordW@@@Z`
- size: `1045`
- prototype: `__int64 __fastcall(struct _DnsNetInfo *, const unsigned __int16 *, unsigned int, __int16, unsigned int, struct _DnsRecordW **)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000d0d0`
- `0x18000ddc0`

## callees

- `0x18000b130`
- `0x18000c640`
- `0x18000cc80`
- `0x18000f390`
- `0x18000f888`
- `0x1800136a0`
- `0x1800150f4`
- `0x1800153f0`
- `0x1800164b8`
- `0x180046ec0`
- `0x180047818`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x18000f467`
- `DNSAPI!DnsNameCompare_W` at `0x18000f467`
- `DNSAPI!NetInfo_GetAdapterByInterfaceIndex` at `0x18000f41e`
- `DNSAPI!NetInfo_GetAdapterByInterfaceIndex` at `0x18000f41e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f70e`

## pseudocode

```c
__int64 __fastcall MDnsGetLocalAandAAAARecords(
        struct _DnsNetInfo *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int16 a4,
        unsigned int a5,
        struct _DnsRecordW **a6)
{
  __int64 AdapterByInterfaceIndex; // rax
  __int64 v11; // r14
  DWORD LastError; // esi
  _QWORD *v13; // rbx
  _QWORD *v14; // rdi
  unsigned int v16; // edi
  __int64 *v17; // r12
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  struct _DnsRecordW *v21; // rax
  __int64 v22; // rsi
  __int128 v23; // xmm6
  __int64 Record; // rsi
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // r13d
  __int64 RecordBasic; // rax
  DWORD NSECRecord; // eax
  __int64 v31[2]; // [rsp+60h] [rbp-268h] BYREF
  WCHAR pName1[256]; // [rsp+70h] [rbp-258h] BYREF

  memset_0(pName1, 0, sizeof(pName1));
  v31[0] = 0;
  if ( !a6 )
  {
    LastError = 87;
    goto LABEL_8;
  }
  *a6 = 0;
  if ( !a2 )
  {
    LastError = 87;
    goto LABEL_8;
  }
  if ( !a1 )
  {
    LastError = 87;
    goto LABEL_8;
  }
  AdapterByInterfaceIndex = NetInfo_GetAdapterByInterfaceIndex(a1, a3, 0);
  v11 = AdapterByInterfaceIndex;
  if ( !AdapterByInterfaceIndex || !*(_QWORD *)(AdapterByInterfaceIndex + 32) )
  {
    LastError = GetLastError();
    goto LABEL_8;
  }
  if ( (int)StringCbPrintfW(pName1, 0x200u, L"%s.local", *((_QWORD *)a1 + 3)) < 0 )
  {
    LastError = 87;
    goto LABEL_8;
  }
  LastError = 0;
  if ( !DnsNameCompare_W(pName1, a2) )
    goto LABEL_8;
  v16 = 0;
  v17 = v31;
  while ( 1 )
  {
    v18 = *(_QWORD *)(v11 + 32);
    v19 = 65533;
    v20 = 1;
    if ( v16 >= *(_DWORD *)(v18 + 4) )
    {
      v21 = (struct _DnsRecordW *)v31[0];
      LastError = 0;
      if ( !v31[0] && (a4 == 23 || a4 == 2) )
      {
        NSECRecord = Dns_CreateNSECRecord(a2, (__int64)v31);
        LastError = NSECRecord;
        if ( NSECRecord )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_d(1035, 88, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, NSECRecord);
          goto LABEL_8;
        }
        v21 = (struct _DnsRecordW *)v31[0];
      }
      *a6 = v21;
      v31[0] = 0;
      goto LABEL_8;
    }
    v22 = v18 + ((unsigned __int64)v16 << 6);
    if ( *(_WORD *)(v22 + 32) == 2 && (a4 & 0xFFFD) == 0 )
    {
      v28 = *(_DWORD *)(v22 + 36);
      RecordBasic = CreateRecordBasic(pName1, 4, 60);
      if ( !RecordBasic )
        goto LABEL_48;
      *(_DWORD *)(RecordBasic + 32) = v28;
      *v17 = RecordBasic;
    }
    if ( *(_WORD *)(v22 + 32) == 23
      && (!a4 || a4 == 23)
      && (*(_BYTE *)(v22 + 40) != 0xFE || (*(_BYTE *)(v22 + 41) & 0xC0) != 0xC0) )
    {
      break;
    }
LABEL_31:
    v27 = *v17;
    if ( *v17 )
    {
      *(_DWORD *)(v27 + 20) &= ~2u;
      *(_DWORD *)(v27 + 20) |= 1u;
      v17 = (__int64 *)*v17;
    }
    ++v16;
  }
  v23 = *(_OWORD *)(v22 + 40);
  Record = Dns_AllocateRecord(16, v20, v19, 28);
  if ( !Record )
    goto LABEL_48;
  v25 = Dns_StringCopyAllocate(pName1, 0, 1);
  if ( v25 )
  {
    *(_QWORD *)(Record + 8) = v25;
    v26 = *(_DWORD *)(Record + 20);
    *(_DWORD *)(Record + 16) = 1048604;
    *(_DWORD *)(Record + 24) = 60;
    *(_DWORD *)(Record + 20) = v26 & 0xFFFFDFE7 | 0x2008;
    *(_OWORD *)(Record + 32) = v23;
    *v17 = Record;
    goto LABEL_31;
  }
  MIDL_user_free((void *)Record);
LABEL_48:
  *v17 = 0;
  LastError = 14;
LABEL_8:
  v13 = (_QWORD *)v31[0];
  if ( g_fVelocityDnsKernelApi )
  {
    Dns_RecordListFree_New(v31[0]);
  }
  else
  {
    if ( (BYTE3(xmmword_1800AB5A0) & 4) != 0 )
      WPP_SF_q(1050, 12, WPP_8a8073b2d2d83a34ea4a6c85ce67b617_Traceguids, v31[0]);
    if ( v13 )
    {
      do
      {
        v14 = (_QWORD *)*v13;
        Dns_RecordFree(v13);
        v13 = v14;
      }
      while ( v14 );
    }
  }
  if ( LastError && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 89, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000f390  mov     r11, rsp
0x18000f393  push    rsi
0x18000f394  sub     rsp, 2C0h
0x18000f39b  mov     rax, cs:__security_cookie
0x18000f3a2  xor     rax, rsp
0x18000f3a5  mov     [rsp+2C8h+var_58], rax
0x18000f3ad  mov     [r11+20h], rbx
0x18000f3b1  mov     esi, r8d
0x18000f3b4  mov     rbx, [rsp+2C8h+arg_28]
0x18000f3bc  mov     r8d, 200h; Size
0x18000f3c2  mov     [r11-10h], rbp
0x18000f3c6  mov     rbp, rdx
0x18000f3c9  mov     [r11-18h], rdi
0x18000f3cd  xor     edx, edx; Val
0x18000f3cf  mov     [r11-28h], r13
0x18000f3d3  mov     rdi, rcx
0x18000f3d6  mov     [r11-38h], r15
0x18000f3da  lea     rcx, [rsp+2C8h+pName1]; void *
0x18000f3df  movzx   r15d, r9w
0x18000f3e3  call    memset_0
0x18000f3e8  xor     r13d, r13d
0x18000f3eb  mov     [rsp+2C8h+var_268], r13
0x18000f3f0  test    rbx, rbx
0x18000f3f3  jz      loc_18000F4FF
0x18000f3f9  mov     [rbx], r13
0x18000f3fc  test    rbp, rbp
0x18000f3ff  jz      loc_18000F704
0x18000f405  test    rdi, rdi
0x18000f408  jz      loc_18000F63B
0x18000f40e  xor     r8d, r8d
0x18000f411  mov     [rsp+2C8h+var_30], r14
0x18000f419  mov     edx, esi
0x18000f41b  mov     rcx, rdi
0x18000f41e  call    cs:__imp_NetInfo_GetAdapterByInterfaceIndex
0x18000f424  mov     r14, rax
0x18000f427  test    rax, rax
0x18000f42a  jz      loc_18000F70E
0x18000f430  cmp     [rax+20h], r13
0x18000f434  jz      loc_18000F6F7
0x18000f43a  mov     r9, [rdi+18h]
0x18000f43e  lea     r8, aSLocal; "%s.local"
0x18000f445  mov     edx, 200h; unsigned __int64
0x18000f44a  lea     rcx, [rsp+2C8h+pName1]; unsigned __int16 *
0x18000f44f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f454  test    eax, eax
0x18000f456  js      loc_18000F72B
0x18000f45c  mov     rdx, rbp; pName2
0x18000f45f  lea     rcx, [rsp+2C8h+pName1]; pName1
0x18000f464  mov     esi, r13d
0x18000f467  call    cs:__imp_DnsNameCompare_W
0x18000f46d  test    eax, eax
0x18000f46f  jnz     loc_18000F509
0x18000f475  mov     r14, [rsp+2C8h+var_30]
0x18000f47d  cmp     cs:g_fVelocityDnsKernelApi, 0
0x18000f484  mov     rbx, [rsp+2C8h+var_268]
0x18000f489  mov     r15, [rsp+2C8h+var_38]
0x18000f491  mov     r13, [rsp+2C8h+var_28]
0x18000f499  mov     rbp, [rsp+2C8h+var_10]
0x18000f4a1  jnz     loc_18000F572
0x18000f4a7  test    byte ptr cs:xmmword_1800AB5A0+3, 4
0x18000f4ae  jnz     loc_18000F6D9
0x18000f4b4  test    rbx, rbx
0x18000f4b7  jz      short loc_18000F4CC
0x18000f4b9  mov     rdi, [rbx]
0x18000f4bc  mov     rcx, rbx
0x18000f4bf  call    Dns_RecordFree
0x18000f4c4  mov     rbx, rdi
0x18000f4c7  test    rdi, rdi
0x18000f4ca  jnz     short loc_18000F4B9
0x18000f4cc  mov     rdi, [rsp+2C8h+var_18]
0x18000f4d4  mov     rbx, [rsp+2C8h+arg_18]
0x18000f4dc  test    esi, esi
0x18000f4de  jnz     loc_18000F77A
0x18000f4e4  mov     eax, esi
0x18000f4e6  mov     rcx, [rsp+2C8h+var_58]
0x18000f4ee  xor     rcx, rsp; StackCookie
0x18000f4f1  call    __security_check_cookie
0x18000f4f6  add     rsp, 2C0h
0x18000f4fd  pop     rsi
0x18000f4fe  retn
0x18000f4ff  mov     esi, 57h ; 'W'
0x18000f504  jmp     loc_18000F47D
0x18000f509  mov     [rsp+2C8h+var_20], r12
0x18000f511  mov     edi, r13d
0x18000f514  lea     r12, [rsp+2C8h+var_268]
0x18000f519  movaps  [rsp+2C8h+var_48], xmm6
0x18000f521  mov     r13d, 10h
0x18000f527  mov     r9d, 1Ch
0x18000f52d  mov     rcx, [r14+20h]
0x18000f531  mov     r8d, 0FFFDh
0x18000f537  mov     edx, 1
0x18000f53c  cmp     edi, [rcx+4]
0x18000f53f  jb      short loc_18000F57F
0x18000f541  mov     rax, [rsp+2C8h+var_268]
0x18000f546  xor     r13d, r13d
0x18000f549  mov     esi, r13d
0x18000f54c  test    rax, rax
0x18000f54f  jz      loc_18000F695
0x18000f555  mov     [rbx], rax
0x18000f558  mov     [rsp+2C8h+var_268], r13
0x18000f55d  movaps  xmm6, [rsp+2C8h+var_48]
0x18000f565  mov     r12, [rsp+2C8h+var_20]
0x18000f56d  jmp     loc_18000F475
0x18000f572  mov     rcx, rbx
0x18000f575  call    Dns_RecordListFree_New
0x18000f57a  jmp     loc_18000F4CC
0x18000f57f  mov     esi, edi
0x18000f581  shl     rsi, 6
0x18000f585  add     rsi, rcx
0x18000f588  cmp     word ptr [rsi+20h], 2
0x18000f58d  jz      loc_18000F645
0x18000f593  cmp     word ptr [rsi+20h], 17h
0x18000f598  jnz     loc_18000F61F
0x18000f59e  test    r15w, r15w
0x18000f5a2  jz      short loc_18000F5AB
0x18000f5a4  cmp     r15w, 17h
0x18000f5a9  jnz     short loc_18000F61F
0x18000f5ab  cmp     byte ptr [rsi+28h], 0FEh
0x18000f5af  jnz     short loc_18000F5BB
0x18000f5b1  movzx   eax, byte ptr [rsi+29h]
0x18000f5b5  and     al, 0C0h
0x18000f5b7  cmp     al, 0C0h
0x18000f5b9  jz      short loc_18000F61F
0x18000f5bb  movups  xmm6, xmmword ptr [rsi+28h]
0x18000f5bf  mov     ecx, r13d
0x18000f5c2  call    Dns_AllocateRecord
0x18000f5c7  mov     rsi, rax
0x18000f5ca  test    rax, rax
0x18000f5cd  jz      loc_18000F73D
0x18000f5d3  mov     r9d, 1
0x18000f5d9  lea     rcx, [rsp+2C8h+pName1]
0x18000f5de  mov     r8d, r9d
0x18000f5e1  xor     edx, edx
0x18000f5e3  call    Dns_StringCopyAllocate
0x18000f5e8  test    rax, rax
0x18000f5eb  jz      loc_18000F735
0x18000f5f1  mov     [rsi+8], rax
0x18000f5f5  mov     r9d, 1Ch
0x18000f5fb  mov     eax, [rsi+14h]
0x18000f5fe  mov     dword ptr [rsi+10h], 10001Ch
0x18000f605  and     eax, 0FFFFFFEFh
0x18000f608  mov     dword ptr [rsi+18h], 3Ch ; '<'
0x18000f60f  or      eax, 2008h
0x18000f614  mov     [rsi+14h], eax
0x18000f617  movups  xmmword ptr [rsi+20h], xmm6
0x18000f61b  mov     [r12], rsi
0x18000f61f  mov     rax, [r12]
0x18000f623  test    rax, rax
0x18000f626  jz      short loc_18000F634
0x18000f628  and     dword ptr [rax+14h], 0FFFFFFFDh
0x18000f62c  or      dword ptr [rax+14h], 1
0x18000f630  mov     r12, [r12]
0x18000f634  inc     edi
0x18000f636  jmp     loc_18000F52D
0x18000f63b  mov     esi, 57h ; 'W'
0x18000f640  jmp     loc_18000F47D
0x18000f645  test    r8w, r15w
0x18000f649  jnz     loc_18000F593
0x18000f64f  mov     r13d, [rsi+24h]
0x18000f653  lea     rcx, [rsp+2C8h+pName1]; lpWideCharStr
0x18000f658  mov     r9d, 4
0x18000f65e  mov     [rsp+2C8h+var_2A0], 3Ch ; '<'; int
0x18000f666  mov     r8d, edx
0x18000f669  mov     dword ptr [rsp+2C8h+var_2A8], r9d; __int16
0x18000f66e  call    CreateRecordBasic
0x18000f673  test    rax, rax
0x18000f676  jz      loc_18000F73D
0x18000f67c  mov     [rax+20h], r13d
0x18000f680  mov     r9d, 1Ch
0x18000f686  mov     [r12], rax
0x18000f68a  mov     r13d, 10h
0x18000f690  jmp     loc_18000F593
0x18000f695  cmp     r15w, 17h
0x18000f69a  jnz     short loc_18000F71B
0x18000f69c  mov     [rsp+2C8h+var_288], dx
0x18000f6a1  cmp     r15w, 17h
0x18000f6a6  jnz     short loc_18000F6AE
0x18000f6a8  mov     [rsp+2C8h+var_288], r9w
0x18000f6ae  lea     rax, [rsp+2C8h+var_268]
0x18000f6b3  mov     rcx, rbp; lpWideCharStr
0x18000f6b6  lea     r8, [rsp+2C8h+var_288]
0x18000f6bb  mov     qword ptr [rsp+2C8h+var_2A8], rax; __int64
0x18000f6c0  call    Dns_CreateNSECRecord
0x18000f6c5  mov     esi, eax
0x18000f6c7  test    eax, eax
0x18000f6c9  jnz     loc_18000F74F
0x18000f6cf  mov     rax, [rsp+2C8h+var_268]
0x18000f6d4  jmp     loc_18000F555
0x18000f6d9  mov     edx, 0Ch
0x18000f6de  lea     r8, WPP_8a8073b2d2d83a34ea4a6c85ce67b617_Traceguids
0x18000f6e5  mov     ecx, 41Ah
0x18000f6ea  mov     r9, rbx
0x18000f6ed  call    WPP_SF_q
0x18000f6f2  jmp     loc_18000F4B4
0x18000f6f7  call    cs:__imp_GetLastError
0x18000f6fd  mov     esi, eax
0x18000f6ff  jmp     loc_18000F475
0x18000f704  mov     esi, 57h ; 'W'
0x18000f709  jmp     loc_18000F47D
0x18000f70e  call    cs:__imp_GetLastError
0x18000f714  mov     esi, eax
0x18000f716  jmp     loc_18000F475
0x18000f71b  cmp     r15w, 2
0x18000f720  jz      loc_18000F69C
0x18000f726  jmp     loc_18000F555
0x18000f72b  mov     esi, 57h ; 'W'
0x18000f730  jmp     loc_18000F475
0x18000f735  mov     rcx, rsi; void *
0x18000f738  call    MIDL_user_free
0x18000f73d  mov     qword ptr [r12], 0
0x18000f745  mov     esi, 0Eh
0x18000f74a  jmp     loc_18000F55D
0x18000f74f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000f756  jz      loc_18000F55D
0x18000f75c  mov     edx, 58h ; 'X'
0x18000f761  lea     r8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x18000f768  mov     ecx, 40Bh
0x18000f76d  mov     r9d, eax
0x18000f770  call    WPP_SF_d
0x18000f775  jmp     loc_18000F55D
0x18000f77a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000f781  jz      loc_18000F4E4
0x18000f787  mov     edx, 59h ; 'Y'
0x18000f78c  lea     r8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x18000f793  mov     ecx, 40Bh
0x18000f798  mov     r9d, esi
0x18000f79b  call    WPP_SF_d
0x18000f7a0  jmp     loc_18000F4E4
```
