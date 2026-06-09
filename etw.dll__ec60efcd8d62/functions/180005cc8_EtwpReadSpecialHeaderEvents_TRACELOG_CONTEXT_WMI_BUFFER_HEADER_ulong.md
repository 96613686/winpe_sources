# EtwpReadSpecialHeaderEvents(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *,ulong)

- ea: `0x180005cc8`
- end: `0x180006034`
- name: `?EtwpReadSpecialHeaderEvents@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@K@Z`
- size: `876`
- prototype: `unsigned int(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18000501c`
- `0x1800052b4`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x18000202c`
- `0x1800030cc`
- `0x180005cc8`
- `0x180012120`
- `0x180012e48`
- `0x180015828`
- `0x180015834`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180005e67`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180005e8b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180005e67`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180005e8b`

## pseudocode

```c
__int64 __fastcall EtwpReadSpecialHeaderEvents(
        struct _TRACELOG_CONTEXT *a1,
        struct _WMI_BUFFER_HEADER *a2,
        unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned int NextEventOffsetType; // esi
  _DWORD *MofData; // rsi
  void *v8; // rax
  void *v9; // rax
  size_t v10; // rbx
  char *v11; // r15
  size_t v12; // rax
  size_t v13; // r14
  char *v14; // r12
  size_t v15; // rbx
  size_t v16; // rax
  size_t v17; // r13
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // kr00_8
  void *v20; // rax
  unsigned __int64 v21; // rax
  void *v22; // rax
  unsigned int *v23; // rbx
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  void *v26; // rax
  _DWORD v28[4]; // [rsp+30h] [rbp-B8h] BYREF
  struct _EVENT_TRACE v29; // [rsp+40h] [rbp-A8h] BYREF

  v3 = a3;
  if ( a3 >= *(_DWORD *)a2 )
    return 0;
  while ( 1 )
  {
    v28[0] = 0;
    NextEventOffsetType = EtwpGetNextEventOffsetType(a2, v3, v28);
    if ( !NextEventOffsetType )
      break;
    v28[0] += v3;
    if ( v28[0] > *((_DWORD *)a2 + 12) )
      return 1392;
    memset_0(&v29, 0, sizeof(v29));
    if ( !EtwpMapEventToEventTrace(0, (char *)a2 + v3, &v29, NextEventOffsetType, a2)
      && !memcmp_0(&v29.Header.Guid, &EventTraceGuid, 0x10u) )
    {
      if ( v29.Header.Class.Type == 80 )
      {
        if ( !*((_QWORD *)a1 + 91) && v29.MofLength >= 0x10 )
        {
          MofData = v29.MofData;
          if ( *(_WORD *)v29.MofData )
          {
            if ( *(_WORD *)v29.MofData == 2 )
            {
              v10 = ((unsigned __int64)v29.MofLength - 16) >> 1;
              v11 = (char *)v29.MofData + 16;
              v12 = wcsnlen((const wchar_t *)v29.MofData + 8, v10);
              v13 = v12;
              if ( v12 != v10 )
              {
                v14 = &v11[2 * v12];
                v15 = v10 - v12 - 1;
                v16 = wcsnlen((const wchar_t *)v14 + 1, v15);
                v17 = v16;
                if ( v16 != v15 )
                {
                  v19 = v16 + 1;
                  v18 = 2 * (v16 + 1);
                  if ( !is_mul_ok(v19, 2u) )
                    v18 = -1;
                  v20 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
                  *((_QWORD *)a1 + 92) = v20;
                  if ( !v20 )
                    return 14;
                  v21 = 2 * (v13 + 1);
                  if ( !is_mul_ok(v13 + 1, 2u) )
                    v21 = -1;
                  v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
                  *((_QWORD *)a1 + 91) = v22;
                  if ( !v22 )
                    return 14;
                  memcpy_0(*((void **)a1 + 92), v14 + 2, 2 * v17 + 2);
                  memcpy_0(*((void **)a1 + 91), MofData + 4, 2 * v13 + 2);
                  *((_DWORD *)a1 + 186) = MofData[1];
                  *((_QWORD *)a1 + 90) = *((_QWORD *)MofData + 1);
                }
              }
            }
          }
          else if ( v29.MofLength >= 0x30 )
          {
            v8 = operator new[](0x4Au, (const struct std::nothrow_t *)&std::nothrow);
            *((_QWORD *)a1 + 92) = v8;
            if ( !v8 )
              return 14;
            v9 = operator new[](0x4Au, (const struct std::nothrow_t *)&std::nothrow);
            *((_QWORD *)a1 + 91) = v9;
            if ( !v9 )
              return 14;
            tlx::guid_to_string_upper<unsigned short>(*((_QWORD *)a1 + 92), MofData + 8);
            tlx::guid_to_string_upper<unsigned short>(*((_QWORD *)a1 + 91), MofData + 4);
            *((_DWORD *)a1 + 186) = MofData[1];
            *((_QWORD *)a1 + 90) = *((_QWORD *)MofData + 1);
          }
        }
      }
      else if ( v29.Header.Class.Type == 82
             && !*((_QWORD *)a1 + 89)
             && v29.MofLength >= 8 * (unsigned __int64)*((unsigned int *)a1 + 216) + 4 )
      {
        v23 = (unsigned int *)v29.MofData;
        v24 = *(unsigned int *)v29.MofData;
        if ( 8 * v24 + 4 <= (unsigned __int64)v29.MofLength )
        {
          v25 = 8 * v24;
          if ( !is_mul_ok(*(unsigned int *)v29.MofData, 8u) )
            v25 = -1;
          v26 = operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
          *((_QWORD *)a1 + 89) = v26;
          if ( !v26 )
            return 14;
          memcpy_0(v26, v23 + 2, 8LL * *v23);
        }
      }
    }
    v3 = v28[0];
    if ( v28[0] >= *(_DWORD *)a2 )
      return 0;
  }
  return 1168;
}

```

## disassembly

```asm
0x180005cc8  mov     [rsp+arg_18], rbx
0x180005ccd  push    rbp
0x180005cce  push    rsi
0x180005ccf  push    rdi
0x180005cd0  push    r12
0x180005cd2  push    r13
0x180005cd4  push    r14
0x180005cd6  push    r15
0x180005cd8  sub     rsp, 0B0h
0x180005cdf  mov     rax, cs:__security_cookie
0x180005ce6  xor     rax, rsp
0x180005ce9  mov     [rsp+0E8h+var_48], rax
0x180005cf1  mov     ebx, r8d
0x180005cf4  mov     rbp, rdx
0x180005cf7  mov     rdi, rcx
0x180005cfa  cmp     r8d, [rdx]
0x180005cfd  jnb     loc_180005FF2
0x180005d03  xor     r14d, r14d
0x180005d06  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005d0a  lea     r15d, [r14+2]
0x180005d0e  lea     r8, [rsp+0E8h+var_B8]
0x180005d13  mov     [rsp+0E8h+var_B8], r14d
0x180005d18  mov     edx, ebx
0x180005d1a  mov     rcx, rbp
0x180005d1d  call    EtwpGetNextEventOffsetType
0x180005d22  mov     esi, eax
0x180005d24  test    eax, eax
0x180005d26  jz      loc_18000602D
0x180005d2c  mov     eax, [rsp+0E8h+var_B8]
0x180005d30  add     eax, ebx
0x180005d32  mov     [rsp+0E8h+var_B8], eax
0x180005d36  cmp     eax, [rbp+30h]
0x180005d39  ja      loc_180006026
0x180005d3f  xor     edx, edx; Val
0x180005d41  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180005d46  lea     r8d, [rdx+58h]; Size
0x180005d4a  call    memset_0
0x180005d4f  mov     edx, ebx
0x180005d51  lea     r8, [rsp+0E8h+var_A8]; struct _EVENT_TRACE *
0x180005d56  add     rdx, rbp; void *
0x180005d59  mov     [rsp+0E8h+var_C8], rbp; struct _WMI_BUFFER_HEADER *
0x180005d5e  mov     r9d, esi; unsigned int
0x180005d61  xor     ecx, ecx; struct _TRACELOG_CONTEXT *
0x180005d63  call    ?EtwpMapEventToEventTrace@@YAKPEAU_TRACELOG_CONTEXT@@PEAXPEAU_EVENT_TRACE@@KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpMapEventToEventTrace(_TRACELOG_CONTEXT *,void *,_EVENT_TRACE *,ulong,_WMI_BUFFER_HEADER *)
0x180005d68  test    eax, eax
0x180005d6a  jnz     loc_180005FE5
0x180005d70  lea     r8d, [rax+10h]; Size
0x180005d74  lea     rdx, EventTraceGuid; Buf2
0x180005d7b  lea     rcx, [rsp+0E8h+var_A8.Header.18h]; Buf1
0x180005d80  call    memcmp_0
0x180005d85  test    eax, eax
0x180005d87  jnz     loc_180005FE5
0x180005d8d  mov     al, byte ptr [rsp+0E8h+var_A8.Header.4]
0x180005d91  cmp     al, 50h ; 'P'
0x180005d93  jnz     loc_180005F55
0x180005d99  cmp     [rdi+2D8h], r14
0x180005da0  jnz     loc_180005FE5
0x180005da6  mov     eax, [rsp+0E8h+var_A8.MofLength]
0x180005dad  cmp     eax, 10h
0x180005db0  jb      loc_180005FE5
0x180005db6  mov     rsi, [rsp+0E8h+var_A8.MofData]
0x180005dbe  cmp     [rsi], r14w
0x180005dc2  jnz     loc_180005E4C
0x180005dc8  cmp     eax, 30h ; '0'
0x180005dcb  jb      loc_180005FE5
0x180005dd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005dd8  mov     ecx, 4Ah ; 'J'; unsigned __int64
0x180005ddd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005de2  mov     [rdi+2E0h], rax
0x180005de9  test    rax, rax
0x180005dec  jz      loc_18000601F
0x180005df2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005df9  mov     ecx, 4Ah ; 'J'; unsigned __int64
0x180005dfe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005e03  mov     [rdi+2D8h], rax
0x180005e0a  test    rax, rax
0x180005e0d  jz      loc_18000601F
0x180005e13  mov     rcx, [rdi+2E0h]
0x180005e1a  lea     rdx, [rsi+20h]
0x180005e1e  call    ??$guid_to_string_upper@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_upper<ushort>(ushort *,_GUID const &,bool)
0x180005e23  mov     rcx, [rdi+2D8h]
0x180005e2a  lea     rdx, [rsi+10h]
0x180005e2e  call    ??$guid_to_string_upper@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_upper<ushort>(ushort *,_GUID const &,bool)
0x180005e33  mov     eax, [rsi+4]
0x180005e36  mov     [rdi+2E8h], eax
0x180005e3c  mov     rax, [rsi+8]
0x180005e40  mov     [rdi+2D0h], rax
0x180005e47  jmp     loc_180005FE5
0x180005e4c  cmp     [rsi], r15w
0x180005e50  jnz     loc_180005FE5
0x180005e56  lea     rbx, [rax-10h]
0x180005e5a  shr     rbx, 1
0x180005e5d  lea     r15, [rsi+10h]
0x180005e61  mov     rdx, rbx; MaxCount
0x180005e64  mov     rcx, r15; Source
0x180005e67  call    cs:__imp_wcsnlen
0x180005e6d  mov     r14, rax
0x180005e70  cmp     rax, rbx
0x180005e73  jz      loc_180005FDC
0x180005e79  sub     rbx, rax
0x180005e7c  lea     r12, [r15+rax*2]
0x180005e80  dec     rbx
0x180005e83  lea     rcx, [r12+2]; Source
0x180005e88  mov     rdx, rbx; MaxCount
0x180005e8b  call    cs:__imp_wcsnlen
0x180005e91  mov     r13, rax
0x180005e94  cmp     rax, rbx
0x180005e97  jz      loc_180005FD3
0x180005e9d  lea     rcx, [rax+1]
0x180005ea1  mov     ebx, 2
0x180005ea6  mov     eax, ebx
0x180005ea8  mul     rcx
0x180005eab  lea     rcx, [rbx-3]
0x180005eaf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005eb6  cmovb   rax, rcx
0x180005eba  mov     rcx, rax; unsigned __int64
0x180005ebd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005ec2  mov     [rdi+2E0h], rax
0x180005ec9  test    rax, rax
0x180005ecc  jz      loc_18000601F
0x180005ed2  lea     rcx, [r14+1]
0x180005ed6  mov     eax, ebx
0x180005ed8  mul     rcx
0x180005edb  lea     rcx, [rbx-3]
0x180005edf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005ee6  cmovb   rax, rcx
0x180005eea  mov     rcx, rax; unsigned __int64
0x180005eed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005ef2  mov     [rdi+2D8h], rax
0x180005ef9  test    rax, rax
0x180005efc  jz      loc_18000601F
0x180005f02  mov     rcx, [rdi+2E0h]; void *
0x180005f09  lea     r8, ds:2[r13*2]; Size
0x180005f11  lea     rdx, [r12+2]; Src
0x180005f16  call    memcpy_0
0x180005f1b  mov     rcx, [rdi+2D8h]; void *
0x180005f22  lea     r8, ds:2[r14*2]; Size
0x180005f2a  mov     rdx, r15; Src
0x180005f2d  call    memcpy_0
0x180005f32  mov     eax, [rsi+4]
0x180005f35  xor     r14d, r14d
0x180005f38  mov     [rdi+2E8h], eax
0x180005f3e  mov     r15d, ebx
0x180005f41  mov     rax, [rsi+8]
0x180005f45  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005f49  mov     [rdi+2D0h], rax
0x180005f50  jmp     loc_180005FE5
0x180005f55  cmp     al, 52h ; 'R'
0x180005f57  jnz     loc_180005FE5
0x180005f5d  cmp     [rdi+2C8h], r14
0x180005f64  jnz     short loc_180005FE5
0x180005f66  mov     eax, [rdi+360h]
0x180005f6c  mov     ecx, [rsp+0E8h+var_A8.MofLength]
0x180005f73  lea     rax, ds:4[rax*8]
0x180005f7b  cmp     rcx, rax
0x180005f7e  jb      short loc_180005FE5
0x180005f80  mov     rbx, [rsp+0E8h+var_A8.MofData]
0x180005f88  mov     edx, [rbx]
0x180005f8a  lea     rax, ds:4[rdx*8]
0x180005f92  cmp     rax, rcx
0x180005f95  ja      short loc_180005FE5
0x180005f97  mov     eax, 8
0x180005f9c  mul     rdx
0x180005f9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005fa6  cmovb   rax, r12
0x180005faa  mov     rcx, rax; unsigned __int64
0x180005fad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005fb2  mov     [rdi+2C8h], rax
0x180005fb9  test    rax, rax
0x180005fbc  jz      short loc_18000601F
0x180005fbe  mov     r8d, [rbx]
0x180005fc1  lea     rdx, [rbx+8]; Src
0x180005fc5  shl     r8, 3; Size
0x180005fc9  mov     rcx, rax; void *
0x180005fcc  call    memcpy_0
0x180005fd1  jmp     short loc_180005FE5
0x180005fd3  xor     r14d, r14d
0x180005fd6  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005fda  jmp     short loc_180005FDF
0x180005fdc  xor     r14d, r14d
0x180005fdf  mov     r15d, 2
0x180005fe5  mov     ebx, [rsp+0E8h+var_B8]
0x180005fe9  cmp     ebx, [rbp+0]
0x180005fec  jb      loc_180005D0E
0x180005ff2  xor     eax, eax
0x180005ff4  mov     rcx, [rsp+0E8h+var_48]
0x180005ffc  xor     rcx, rsp; StackCookie
0x180005fff  call    __security_check_cookie
0x180006004  mov     rbx, [rsp+0E8h+arg_18]
0x18000600c  add     rsp, 0B0h
0x180006013  pop     r15
0x180006015  pop     r14
0x180006017  pop     r13
0x180006019  pop     r12
0x18000601b  pop     rdi
0x18000601c  pop     rsi
0x18000601d  pop     rbp
0x18000601e  retn
0x18000601f  mov     eax, 0Eh
0x180006024  jmp     short loc_180005FF4
0x180006026  mov     eax, 570h
0x18000602b  jmp     short loc_180005FF4
0x18000602d  mov     eax, 490h
0x180006032  jmp     short loc_180005FF4
```
