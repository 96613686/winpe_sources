# IASComputeResponse

- ea: `0x18001be60`
- end: `0x18001c0bd`
- name: `IASComputeResponse`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c570`

## callees

- `0x180002ec8`
- `0x180006a20`
- `0x180013b20`
- `0x18001be60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001c07b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001c07b`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf5a`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf7d`
- `ntdll!RtlNtStatusToDosError` at `0x18001bfb1`
- `ntdll!RtlNtStatusToDosError` at `0x18001c013`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf5a`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf7d`
- `ntdll!RtlNtStatusToDosError` at `0x18001bfb1`
- `ntdll!RtlNtStatusToDosError` at `0x18001c013`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bedc`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bedc`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf3e`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf3e`
- `CRYPTSP!SystemFunction009` at `0x18001bf93`
- `CRYPTSP!SystemFunction009` at `0x18001bf93`
- `CRYPTSP!SystemFunction007` at `0x18001bf19`
- `CRYPTSP!SystemFunction007` at `0x18001bf19`
- `CRYPTSP!SystemFunction011` at `0x18001bff5`
- `CRYPTSP!SystemFunction011` at `0x18001bff5`

## pseudocode

```c
int __fastcall IASComputeResponse(__int64 a1, const char *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 MaximumLength; // rcx
  unsigned int v12; // edi
  PWSTR Buffer; // rax
  __int64 v14; // rbx
  ULONG v15; // eax
  NTSTATUS v16; // eax
  __int64 v17; // rbx
  ULONG v18; // eax
  __int64 v19; // rax
  __int128 *v20; // rcx
  NTSTATUS v21; // eax
  __int64 v22; // rbx
  ULONG v23; // eax
  __int64 v24; // rax
  __int128 *v25; // rcx
  __int64 v26; // xmm1_8
  __int128 v27; // xmm0
  __int128 *v28; // rcx
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-50h] BYREF
  __int128 v31; // [rsp+40h] [rbp-40h] BYREF
  __int128 v32; // [rsp+50h] [rbp-30h] BYREF
  __int64 v33; // [rsp+60h] [rbp-20h]
  __int128 v34; // [rsp+68h] [rbp-18h] BYREF

  Destination = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids);
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, a2) )
  {
    v10 = SystemFunction007(&Destination, &v31);
    MaximumLength = Destination.MaximumLength;
    v12 = v10;
    Buffer = Destination.Buffer;
    if ( Destination.MaximumLength )
    {
      do
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (PWSTR)((char *)Buffer + 1);
        --MaximumLength;
      }
      while ( MaximumLength );
    }
    RtlFreeUnicodeString(&Destination);
    if ( (v12 & 0x80000000) == 0 )
    {
      v16 = SystemFunction009(a3, &v31, &v32);
      v12 = v16;
      if ( v16 >= 0 )
      {
        v21 = SystemFunction011(&v32, &v31, &v34);
        v12 = v21;
        if ( v21 >= 0 )
        {
          v26 = v33;
          *(_OWORD *)a4 = v32;
          v27 = v34;
          *(_QWORD *)(a4 + 16) = v26;
          *(_OWORD *)(a5 + 514) = v27;
          _o_wcsncpy_s(a5, 257, a1, 256);
          v28 = &v31;
          *(_WORD *)(a5 + 512) = 0;
          v9 = 16;
          do
          {
            *(_BYTE *)v28 = 0;
            v28 = (__int128 *)((char *)v28 + 1);
            --v9;
          }
          while ( v9 );
          return v9;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v23 = RtlNtStatusToDosError(v21);
          WPP_SF_dd(v22, 31, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, v12, v23);
        }
        v24 = 16;
        v25 = &v31;
        do
        {
          *(_BYTE *)v25 = 0;
          v25 = (__int128 *)((char *)v25 + 1);
          --v24;
        }
        while ( v24 );
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v18 = RtlNtStatusToDosError(v16);
          WPP_SF_dd(v17, 30, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, v12, v18);
        }
        v19 = 16;
        v20 = &v31;
        do
        {
          *(_BYTE *)v20 = 0;
          v20 = (__int128 *)((char *)v20 + 1);
          --v19;
        }
        while ( v19 );
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v15 = RtlNtStatusToDosError(v12);
      WPP_SF_dd(v14, 29, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, v12, v15);
    }
    LODWORD(v9) = RtlNtStatusToDosError(v12);
    return v9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids);
  LODWORD(v9) = 87;
  return v9;
}

```

## disassembly

```asm
0x18001be60  push    rbp
0x18001be62  push    rbx
0x18001be63  push    rsi
0x18001be64  push    rdi
0x18001be65  push    r13
0x18001be67  push    r14
0x18001be69  push    r15
0x18001be6b  mov     rbp, rsp
0x18001be6e  sub     rsp, 80h
0x18001be75  mov     rax, cs:__security_cookie
0x18001be7c  xor     rax, rsp
0x18001be7f  mov     [rbp+var_8], rax
0x18001be83  mov     rbx, [rbp+arg_20]
0x18001be87  xorps   xmm0, xmm0
0x18001be8a  xorps   xmm1, xmm1
0x18001be8d  xor     eax, eax
0x18001be8f  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18001be93  mov     [rbp+var_20], rax
0x18001be97  mov     rsi, r9
0x18001be9a  movups  [rbp+var_40], xmm1
0x18001be9e  mov     r14, r8
0x18001bea1  mov     rdi, rdx
0x18001bea4  movups  [rbp+var_30], xmm0
0x18001bea8  mov     r15, rcx
0x18001beab  movups  [rbp+var_18], xmm0
0x18001beaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beb6  lea     r13, WPP_GLOBAL_Control
0x18001bebd  cmp     rcx, r13
0x18001bec0  jz      short loc_18001BED5
0x18001bec2  mov     rcx, [rcx+10h]
0x18001bec6  lea     edx, [rax+1Bh]
0x18001bec9  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001bed0  call    WPP_SF_
0x18001bed5  mov     rdx, rdi; Source
0x18001bed8  lea     rcx, [rbp+Destination]; Destination
0x18001bedc  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001bee2  test    al, al
0x18001bee4  jnz     short loc_18001BF11
0x18001bee6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beed  cmp     rcx, r13
0x18001bef0  jz      short loc_18001BF07
0x18001bef2  mov     rcx, [rcx+10h]
0x18001bef6  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001befd  mov     edx, 1Ch
0x18001bf02  call    WPP_SF_
0x18001bf07  mov     eax, 57h ; 'W'
0x18001bf0c  jmp     loc_18001C09F
0x18001bf11  lea     rdx, [rbp+var_40]
0x18001bf15  lea     rcx, [rbp+Destination]
0x18001bf19  call    cs:__imp_SystemFunction007
0x18001bf1f  movzx   ecx, [rbp+Destination.MaximumLength]
0x18001bf23  mov     edi, eax
0x18001bf25  mov     rax, [rbp+Destination.Buffer]
0x18001bf29  test    rcx, rcx
0x18001bf2c  jz      short loc_18001BF3A
0x18001bf2e  mov     byte ptr [rax], 0
0x18001bf31  inc     rax
0x18001bf34  sub     rcx, 1
0x18001bf38  jnz     short loc_18001BF2E
0x18001bf3a  lea     rcx, [rbp+Destination]; UnicodeString
0x18001bf3e  call    cs:__imp_RtlFreeUnicodeString
0x18001bf44  test    edi, edi
0x18001bf46  jns     short loc_18001BF88
0x18001bf48  mov     rbx, cs:WPP_GLOBAL_Control
0x18001bf4f  cmp     rbx, r13
0x18001bf52  jz      short loc_18001BF7B
0x18001bf54  mov     rbx, [rbx+10h]
0x18001bf58  mov     ecx, edi; Status
0x18001bf5a  call    cs:__imp_RtlNtStatusToDosError
0x18001bf60  mov     edx, 1Dh
0x18001bf65  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001bf6c  mov     r9d, edi
0x18001bf6f  mov     [rsp+80h+var_60], eax
0x18001bf73  mov     rcx, rbx
0x18001bf76  call    WPP_SF_dd
0x18001bf7b  mov     ecx, edi; Status
0x18001bf7d  call    cs:__imp_RtlNtStatusToDosError
0x18001bf83  jmp     loc_18001C09F
0x18001bf88  lea     r8, [rbp+var_30]
0x18001bf8c  mov     rcx, r14
0x18001bf8f  lea     rdx, [rbp+var_40]
0x18001bf93  call    cs:__imp_SystemFunction009
0x18001bf99  mov     edi, eax
0x18001bf9b  test    eax, eax
0x18001bf9d  jns     short loc_18001BFE9
0x18001bf9f  mov     rbx, cs:WPP_GLOBAL_Control
0x18001bfa6  cmp     rbx, r13
0x18001bfa9  jz      short loc_18001BFD2
0x18001bfab  mov     rbx, [rbx+10h]
0x18001bfaf  mov     ecx, eax; Status
0x18001bfb1  call    cs:__imp_RtlNtStatusToDosError
0x18001bfb7  mov     edx, 1Eh
0x18001bfbc  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001bfc3  mov     r9d, edi
0x18001bfc6  mov     [rsp+80h+var_60], eax
0x18001bfca  mov     rcx, rbx
0x18001bfcd  call    WPP_SF_dd
0x18001bfd2  mov     eax, 10h
0x18001bfd7  lea     rcx, [rbp+var_40]
0x18001bfdb  mov     byte ptr [rcx], 0
0x18001bfde  inc     rcx
0x18001bfe1  sub     rax, 1
0x18001bfe5  jnz     short loc_18001BFDB
0x18001bfe7  jmp     short loc_18001BF7B
0x18001bfe9  lea     r8, [rbp+var_18]
0x18001bfed  lea     rdx, [rbp+var_40]
0x18001bff1  lea     rcx, [rbp+var_30]
0x18001bff5  call    cs:__imp_SystemFunction011
0x18001bffb  mov     edi, eax
0x18001bffd  test    eax, eax
0x18001bfff  jns     short loc_18001C04E
0x18001c001  mov     rbx, cs:WPP_GLOBAL_Control
0x18001c008  cmp     rbx, r13
0x18001c00b  jz      short loc_18001C034
0x18001c00d  mov     rbx, [rbx+10h]
0x18001c011  mov     ecx, eax; Status
0x18001c013  call    cs:__imp_RtlNtStatusToDosError
0x18001c019  mov     edx, 1Fh
0x18001c01e  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001c025  mov     r9d, edi
0x18001c028  mov     [rsp+80h+var_60], eax
0x18001c02c  mov     rcx, rbx
0x18001c02f  call    WPP_SF_dd
0x18001c034  mov     eax, 10h
0x18001c039  lea     rcx, [rbp+var_40]
0x18001c03d  mov     byte ptr [rcx], 0
0x18001c040  inc     rcx
0x18001c043  sub     rax, 1
0x18001c047  jnz     short loc_18001C03D
0x18001c049  jmp     loc_18001BF7B
0x18001c04e  movups  xmm0, [rbp+var_30]
0x18001c052  mov     r9d, 100h
0x18001c058  mov     r8, r15
0x18001c05b  movsd   xmm1, [rbp+var_20]
0x18001c060  mov     rcx, rbx
0x18001c063  movups  xmmword ptr [rsi], xmm0
0x18001c066  movups  xmm0, [rbp+var_18]
0x18001c06a  lea     edx, [r9+1]
0x18001c06e  movsd   qword ptr [rsi+10h], xmm1
0x18001c073  movdqu  xmmword ptr [rbx+202h], xmm0
0x18001c07b  call    cs:__imp__o_wcsncpy_s
0x18001c081  xor     eax, eax
0x18001c083  lea     rcx, [rbp+var_40]
0x18001c087  mov     [rbx+200h], ax
0x18001c08e  mov     eax, 10h
0x18001c093  mov     byte ptr [rcx], 0
0x18001c096  inc     rcx
0x18001c099  sub     rax, 1
0x18001c09d  jnz     short loc_18001C093
0x18001c09f  mov     rcx, [rbp+var_8]
0x18001c0a3  xor     rcx, rsp; StackCookie
0x18001c0a6  call    __security_check_cookie
0x18001c0ab  add     rsp, 80h
0x18001c0b2  pop     r15
0x18001c0b4  pop     r14
0x18001c0b6  pop     r13
0x18001c0b8  pop     rdi
0x18001c0b9  pop     rsi
0x18001c0ba  pop     rbx
0x18001c0bb  pop     rbp
0x18001c0bc  retn
```
