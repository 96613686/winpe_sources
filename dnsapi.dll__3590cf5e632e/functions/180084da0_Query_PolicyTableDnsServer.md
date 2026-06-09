# Query_PolicyTableDnsServer

- ea: `0x180084da0`
- end: `0x1800851ce`
- name: `Query_PolicyTableDnsServer`
- size: `1070`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004c58c`
- `0x18009e3dc`

## callees

- `0x18001b75c`
- `0x18001bd54`
- `0x18002e894`
- `0x1800317e0`
- `0x18004a0b0`
- `0x18004ef50`
- `0x18006ea9c`
- `0x180083954`
- `0x180084da0`
- `0x18009e728`
- `0x1800cc528`
- `0x1800dbadc`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008511b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008511b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180084e3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180084e3d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180084f5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180084f5a`

## pseudocode

```c
__int64 __fastcall Query_PolicyTableDnsServer(__int64 a1, __int64 *a2, LPVOID *a3)
{
  DWORD LastError; // edi
  __int64 QueryBlob; // rbx
  unsigned int v8; // r13d
  HANDLE EventW; // rcx
  __int64 v10; // rax
  __int64 *i; // rcx
  __int64 v12; // rax
  __int64 *v13; // rsi
  __int64 v14; // rax
  void *v15; // rcx

  if ( !a1 )
    return 87;
  if ( !*(_QWORD *)(a1 + 1128) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    return 87;
  }
  QueryBlob = 0;
  v8 = 0;
  LastError = 0;
  while ( a2 )
  {
    if ( *((_BYTE *)a2 + 8) )
    {
      if ( QueryBlob )
        DeRefQueryBlobEx((char *)QueryBlob, (__int64)"Query_PolicyTableDnsServer", 119, 10);
      QueryBlob = Query_AllocateQueryBlob(10);
      if ( !QueryBlob )
        return 14;
      EventW = CreateEventW(0, 1, 0, 0);
      if ( !EventW )
      {
        LastError = GetLastError();
        goto LABEL_56;
      }
      *(_WORD *)(QueryBlob + 256) = 28;
      v10 = 20640;
      *(_QWORD *)(QueryBlob + 232) = (char *)a2 + 10;
      *(_QWORD *)(QueryBlob + 240) = (char *)a2 + 10;
      *(_QWORD *)(QueryBlob + 264) = 20640;
      if ( (*(_QWORD *)(a1 + 264) & 0x80000000000000LL) != 0 )
      {
        v10 = 0x800000000050A0LL;
        *(_QWORD *)(QueryBlob + 264) = 0x800000000050A0LL;
      }
      *(_DWORD *)(QueryBlob + 392) |= 0x41u;
      *(_QWORD *)(QueryBlob + 600) = v10;
      *(_QWORD *)(QueryBlob + 1168) = EventW;
      *(_QWORD *)(QueryBlob + 1128) = *(_QWORD *)(a1 + 1128);
      *(_DWORD *)(QueryBlob + 344) = *(_DWORD *)(a1 + 344);
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_S(1035, 364, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, (char *)a2 + 10);
      if ( *(_QWORD *)(a1 + 1144) )
      {
        *(_QWORD *)(QueryBlob + 1072) = *(_QWORD *)(a1 + 1072);
        *(_QWORD *)(QueryBlob + 1080) = *(_QWORD *)(a1 + 1080);
        *(_QWORD *)(QueryBlob + 1088) = *(_QWORD *)(a1 + 1088);
        (*(void (__fastcall **)(__int64))(a1 + 1144))(QueryBlob);
        goto LABEL_19;
      }
      *(_DWORD *)(QueryBlob + 396) = *(_DWORD *)(a1 + 396);
      LastError = Query_InProcess((LPVOID)QueryBlob);
      if ( LastError == 9506 )
      {
LABEL_19:
        WaitForSingleObject(*(HANDLE *)(QueryBlob + 1168), 0xFFFFFFFF);
        LastError = *(_DWORD *)(QueryBlob + 508);
      }
      if ( LastError )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_Sd(
            1035,
            368,
            (unsigned int)WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids,
            (_DWORD)a2 + 10,
            LastError);
      }
      else
      {
        for ( i = *(__int64 **)(QueryBlob + 960); i; i = (__int64 *)*i )
        {
          if ( (*((_DWORD *)i + 5) & 3u) <= 1 && (*((_WORD *)i + 8) == 1 || *((_WORD *)i + 8) == 28) )
            ++v8;
        }
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 365, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v8);
        if ( v8 )
        {
          v12 = DnsAddrArray_CopyAndExpand(*a3);
          *a3 = (LPVOID)v12;
          if ( !v12 )
          {
            LastError = 14;
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_DS(1035, 366, (unsigned int)WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, 14, (__int64)a2 + 10);
            goto LABEL_56;
          }
          LastError = 0;
        }
        v13 = *(__int64 **)(QueryBlob + 960);
        Dns_RecordListUnmapV4MappedAAAAInPlace(v13);
        while ( v13 )
        {
          if ( (*((_DWORD *)v13 + 5) & 3u) <= 1
            && (*((_WORD *)v13 + 8) == 1 || *((_WORD *)v13 + 8) == 28)
            && !(unsigned int)DnsAddrArray_AddAddrFromDnsRecord(*a3, v13) )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_S(1035, 367, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, (char *)a2 + 10);
            break;
          }
          v13 = (__int64 *)*v13;
        }
      }
      Dns_RecordListFree(*(LPVOID *)(QueryBlob + 960));
      *(_QWORD *)(QueryBlob + 960) = 0;
      goto LABEL_46;
    }
    v14 = DnsAddrArray_CopyAndExpand(*a3);
    *a3 = (LPVOID)v14;
    if ( !v14 )
    {
      LastError = 14;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_d(1035, 369, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, 14);
      break;
    }
    LastError = 0;
    if ( !(unsigned int)DnsAddrArray_AddAddr(v14, (char *)a2 + 10, 0, 0) )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 370, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids);
      break;
    }
LABEL_46:
    a2 = (__int64 *)*a2;
  }
  if ( !QueryBlob )
    return LastError;
LABEL_56:
  v15 = *(void **)(QueryBlob + 960);
  if ( v15 )
  {
    Dns_RecordListFree(v15);
    *(_QWORD *)(QueryBlob + 960) = 0;
  }
  DeRefQueryBlobEx((char *)QueryBlob, (__int64)"Query_PolicyTableDnsServer", 27, 10);
  return LastError;
}

```

## disassembly

```asm
0x180084da0  push    rbx
0x180084da2  push    rbp
0x180084da3  push    rsi
0x180084da4  push    rdi
0x180084da5  push    r12
0x180084da7  push    r13
0x180084da9  push    r14
0x180084dab  push    r15
0x180084dad  sub     rsp, 38h
0x180084db1  mov     r12, r8
0x180084db4  mov     r14, rdx
0x180084db7  mov     rbp, rcx
0x180084dba  test    rcx, rcx
0x180084dbd  jnz     short loc_180084DC9
0x180084dbf  mov     edi, 57h ; 'W'
0x180084dc4  jmp     loc_1800851BA
0x180084dc9  cmp     qword ptr [rcx+468h], 0
0x180084dd1  jnz     short loc_180084DDA
0x180084dd3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180084dd8  jmp     short loc_180084DBF
0x180084dda  xor     ebx, ebx
0x180084ddc  xor     r13d, r13d
0x180084ddf  xor     edi, edi
0x180084de1  mov     sil, 8
0x180084de4  lea     r15d, [rbx+1]
0x180084de8  test    r14, r14
0x180084deb  jz      loc_18008517E
0x180084df1  cmp     byte ptr [r14+8], 0
0x180084df6  jz      loc_1800850AC
0x180084dfc  test    rbx, rbx
0x180084dff  jz      short loc_180084E1C
0x180084e01  mov     r9d, 0Ah
0x180084e07  lea     rdx, aQueryPolicytab; "Query_PolicyTableDnsServer"
0x180084e0e  mov     r8d, 2D77h
0x180084e14  mov     rcx, rbx; lpMem
0x180084e17  call    DeRefQueryBlobEx
0x180084e1c  mov     ecx, 0Ah
0x180084e21  call    Query_AllocateQueryBlob
0x180084e26  mov     rbx, rax
0x180084e29  test    rax, rax
0x180084e2c  jz      loc_18008512B
0x180084e32  xor     r9d, r9d; lpName
0x180084e35  xor     r8d, r8d; bInitialState
0x180084e38  mov     edx, r15d; bManualReset
0x180084e3b  xor     ecx, ecx; lpEventAttributes
0x180084e3d  call    cs:__imp_CreateEventW
0x180084e44  nop     dword ptr [rax+rax+00h]
0x180084e49  mov     rcx, rax
0x180084e4c  test    rax, rax
0x180084e4f  jz      loc_18008511B
0x180084e55  lea     r15, [r14+0Ah]
0x180084e59  mov     word ptr [rbx+100h], 1Ch
0x180084e62  mov     eax, 50A0h
0x180084e67  mov     [rbx+0E8h], r15
0x180084e6e  mov     rdx, 80000000000000h
0x180084e78  mov     [rbx+0F0h], r15
0x180084e7f  mov     [rbx+108h], rax
0x180084e86  test    [rbp+108h], rdx
0x180084e8d  jz      short loc_180084EA0
0x180084e8f  mov     rax, 800000000050A0h
0x180084e99  mov     [rbx+108h], rax
0x180084ea0  or      dword ptr [rbx+188h], 41h
0x180084ea7  mov     [rbx+258h], rax
0x180084eae  mov     [rbx+490h], rcx
0x180084eb5  mov     rax, [rbp+468h]
0x180084ebc  mov     [rbx+468h], rax
0x180084ec3  mov     eax, [rbp+158h]
0x180084ec9  mov     [rbx+158h], eax
0x180084ecf  test    byte ptr cs:xmmword_1801119E0+1, sil
0x180084ed6  jz      short loc_180084EF1
0x180084ed8  mov     edx, 16Ch
0x180084edd  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180084ee4  mov     ecx, 40Bh
0x180084ee9  mov     r9, r15
0x180084eec  call    WPP_SF_S
0x180084ef1  cmp     qword ptr [rbp+478h], 0
0x180084ef9  mov     rcx, rbx; lpMem
0x180084efc  jz      short loc_180084F36
0x180084efe  mov     rax, [rbp+430h]
0x180084f05  mov     [rbx+430h], rax
0x180084f0c  mov     rax, [rbp+438h]
0x180084f13  mov     [rbx+438h], rax
0x180084f1a  mov     rax, [rbp+440h]
0x180084f21  mov     [rbx+440h], rax
0x180084f28  mov     rax, [rbp+478h]
0x180084f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084f34  jmp     short loc_180084F50
0x180084f36  mov     eax, [rbp+18Ch]
0x180084f3c  mov     [rbx+18Ch], eax
0x180084f42  call    Query_InProcess
0x180084f47  mov     edi, eax
0x180084f49  cmp     eax, 2522h
0x180084f4e  jnz     short loc_180084F6C
0x180084f50  mov     rcx, [rbx+490h]; hHandle
0x180084f57  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180084f5a  call    cs:__imp_WaitForSingleObject
0x180084f61  nop     dword ptr [rax+rax+00h]
0x180084f66  mov     edi, [rbx+1FCh]
0x180084f6c  test    edi, edi
0x180084f6e  jnz     loc_180085062
0x180084f74  mov     rcx, [rbx+3C0h]
0x180084f7b  test    rcx, rcx
0x180084f7e  jz      short loc_180084FA9
0x180084f80  lea     edx, [rdi+1]
0x180084f83  lea     esi, [rdi+1Ch]
0x180084f86  mov     eax, [rcx+14h]
0x180084f89  and     al, 3
0x180084f8b  cmp     al, dl
0x180084f8d  ja      short loc_180084F9E
0x180084f8f  cmp     [rcx+10h], dx
0x180084f93  jz      short loc_180084F9B
0x180084f95  cmp     [rcx+10h], si
0x180084f99  jnz     short loc_180084F9E
0x180084f9b  add     r13d, edx
0x180084f9e  mov     rcx, [rcx]
0x180084fa1  test    rcx, rcx
0x180084fa4  jnz     short loc_180084F86
0x180084fa6  mov     sil, 8
0x180084fa9  test    byte ptr cs:xmmword_1801119E0+1, sil
0x180084fb0  jz      short loc_180084FCB
0x180084fb2  mov     edx, 16Dh
0x180084fb7  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180084fbe  mov     ecx, 40Bh
0x180084fc3  mov     r9d, r13d
0x180084fc6  call    WPP_SF_d
0x180084fcb  test    r13d, r13d
0x180084fce  jz      short loc_180084FF1
0x180084fd0  mov     rcx, [r12]; lpMem
0x180084fd4  mov     r8d, 1
0x180084fda  mov     edx, r13d
0x180084fdd  call    DnsAddrArray_CopyAndExpand
0x180084fe2  mov     [r12], rax
0x180084fe6  test    rax, rax
0x180084fe9  jz      loc_1800850E8
0x180084fef  xor     edi, edi
0x180084ff1  mov     rsi, [rbx+3C0h]
0x180084ff8  mov     rcx, rsi
0x180084ffb  call    Dns_RecordListUnmapV4MappedAAAAInPlace
0x180085000  test    rsi, rsi
0x180085003  jz      loc_18008508A
0x180085009  mov     eax, [rsi+14h]
0x18008500c  mov     ecx, 1
0x180085011  and     al, 3
0x180085013  cmp     al, cl
0x180085015  ja      short loc_180085036
0x180085017  cmp     [rsi+10h], cx
0x18008501b  jz      short loc_180085026
0x18008501d  lea     eax, [rcx+1Bh]
0x180085020  cmp     [rsi+10h], ax
0x180085024  jnz     short loc_180085036
0x180085026  mov     rcx, [r12]
0x18008502a  mov     rdx, rsi
0x18008502d  call    DnsAddrArray_AddAddrFromDnsRecord
0x180085032  test    eax, eax
0x180085034  jz      short loc_18008503B
0x180085036  mov     rsi, [rsi]
0x180085039  jmp     short loc_180085000
0x18008503b  mov     sil, 8
0x18008503e  test    byte ptr cs:xmmword_1801119E0+1, sil
0x180085045  jz      short loc_18008508D
0x180085047  mov     edx, 16Fh
0x18008504c  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180085053  mov     ecx, 40Bh
0x180085058  mov     r9, r15
0x18008505b  call    WPP_SF_S
0x180085060  jmp     short loc_18008508D
0x180085062  test    byte ptr cs:xmmword_1801119E0+1, sil
0x180085069  jz      short loc_18008508D
0x18008506b  mov     edx, 170h
0x180085070  mov     dword ptr [rsp+78h+var_58], edi
0x180085074  mov     ecx, 40Bh
0x180085079  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180085080  mov     r9, r15
0x180085083  call    WPP_SF_Sd
0x180085088  jmp     short loc_18008508D
0x18008508a  mov     sil, 8
0x18008508d  mov     rcx, [rbx+3C0h]; lpMem
0x180085094  call    Dns_RecordListFree
0x180085099  mov     qword ptr [rbx+3C0h], 0
0x1800850a4  mov     r15d, 1
0x1800850aa  jmp     short loc_1800850E0
0x1800850ac  mov     rcx, [r12]; lpMem
0x1800850b0  mov     r8d, r15d
0x1800850b3  mov     edx, r15d
0x1800850b6  call    DnsAddrArray_CopyAndExpand
0x1800850bb  mov     [r12], rax
0x1800850bf  test    rax, rax
0x1800850c2  jz      loc_180085156
0x1800850c8  lea     rdx, [r14+0Ah]
0x1800850cc  xor     r9d, r9d
0x1800850cf  xor     r8d, r8d
0x1800850d2  mov     rcx, rax
0x1800850d5  xor     edi, edi
0x1800850d7  call    DnsAddrArray_AddAddr
0x1800850dc  test    eax, eax
0x1800850de  jz      short loc_180085135
0x1800850e0  mov     r14, [r14]
0x1800850e3  jmp     loc_180084DE8
0x1800850e8  mov     r9d, 0Eh
0x1800850ee  mov     edi, r9d
0x1800850f1  test    byte ptr cs:xmmword_1801119E0+1, sil
0x1800850f8  jz      loc_180085183
0x1800850fe  mov     edx, 16Eh
0x180085103  mov     [rsp+78h+var_58], r15
0x180085108  mov     ecx, 40Bh
0x18008510d  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180085114  call    WPP_SF_DS
0x180085119  jmp     short loc_180085183
0x18008511b  call    cs:__imp_GetLastError
0x180085122  nop     dword ptr [rax+rax+00h]
0x180085127  mov     edi, eax
0x180085129  jmp     short loc_180085183
0x18008512b  mov     edi, 0Eh
0x180085130  jmp     loc_1800851BA
0x180085135  test    byte ptr cs:xmmword_1801119E0+1, sil
0x18008513c  jz      short loc_18008517E
0x18008513e  mov     edx, 172h
0x180085143  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x18008514a  mov     ecx, 40Bh
0x18008514f  call    WPP_SF_
0x180085154  jmp     short loc_18008517E
0x180085156  mov     r9d, 0Eh
0x18008515c  mov     edi, r9d
0x18008515f  test    byte ptr cs:xmmword_1801119E0+1, sil
0x180085166  jz      short loc_18008517E
0x180085168  mov     edx, 171h
0x18008516d  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180085174  mov     ecx, 40Bh
0x180085179  call    WPP_SF_d
0x18008517e  test    rbx, rbx
0x180085181  jz      short loc_1800851BA
0x180085183  mov     rcx, [rbx+3C0h]; lpMem
0x18008518a  test    rcx, rcx
0x18008518d  jz      short loc_18008519F
0x18008518f  call    Dns_RecordListFree
0x180085194  mov     qword ptr [rbx+3C0h], 0
0x18008519f  mov     r9d, 0Ah
0x1800851a5  lea     rdx, aQueryPolicytab; "Query_PolicyTableDnsServer"
0x1800851ac  mov     r8d, 2E1Bh
0x1800851b2  mov     rcx, rbx; lpMem
0x1800851b5  call    DeRefQueryBlobEx
0x1800851ba  mov     eax, edi
0x1800851bc  add     rsp, 38h
0x1800851c0  pop     r15
0x1800851c2  pop     r14
0x1800851c4  pop     r13
0x1800851c6  pop     r12
0x1800851c8  pop     rdi
0x1800851c9  pop     rsi
0x1800851ca  pop     rbp
0x1800851cb  pop     rbx
0x1800851cc  retn
```
