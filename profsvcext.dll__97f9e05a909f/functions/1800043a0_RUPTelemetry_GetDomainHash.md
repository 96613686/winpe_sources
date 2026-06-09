# RUPTelemetry::GetDomainHash

- ea: `0x1800043a0`
- end: `0x18000457c`
- name: `RUPTelemetry::GetDomainHash`
- size: `476`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004660`
- `0x180006344`
- `0x180015290`
- `0x180015f30`

## callees

- `0x1800043a0`
- `0x180006a9c`
- `0x1800139ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004569`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000455b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000455b`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180004513`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180004513`
- `logoncli!DsGetDcNameW` at `0x1800043e2`
- `logoncli!DsGetDcNameW` at `0x1800043e2`
- `netutils!NetApiBufferFree` at `0x180004409`
- `netutils!NetApiBufferFree` at `0x18000443f`
- `netutils!NetApiBufferFree` at `0x180004484`
- `netutils!NetApiBufferFree` at `0x1800044a3`
- `netutils!NetApiBufferFree` at `0x180004409`
- `netutils!NetApiBufferFree` at `0x18000443f`
- `netutils!NetApiBufferFree` at `0x180004484`
- `netutils!NetApiBufferFree` at `0x1800044a3`

## string_xrefs

- `0x18000441d`: `clientcore\ds\security\gina\profile\roaming\RUPTelemetryHelpers.h`
- `0x180004466`: `clientcore\ds\security\gina\profile\roaming\RUPTelemetryHelpers.h`

## pseudocode

```c
__int64 RUPTelemetry::GetDomainHash()
{
  unsigned int v0; // ebx
  LPWSTR v1; // rdi
  signed int DcNameW; // eax
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rsi
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  unsigned int i; // ebx
  int v9; // ecx
  HANDLE ProcessHeap; // rax
  LPWSTR lpsz; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h]
  __int64 v14; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID Buffer; // [rsp+60h] [rbp+8h] BYREF

  v13 = -1;
  v0 = 0;
  v1 = 0;
  v14 = -1;
  lpsz = 0;
  Buffer = 0;
  DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x40008100u, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
  if ( DcNameW > 0 )
    DcNameW = (unsigned __int16)DcNameW | 0x80070000;
  if ( DcNameW == -2147023541 )
  {
    if ( Buffer )
      NetApiBufferFree(Buffer);
  }
  else
  {
    if ( DcNameW >= 0 )
    {
      v3 = HeapAllocString(*((const unsigned __int16 **)Buffer + 5), &lpsz);
      if ( v3 >= 0 )
      {
        if ( Buffer )
          NetApiBufferFree(Buffer);
        v4 = v13;
        v1 = lpsz;
        if ( v13 == -1 )
        {
          if ( lpsz )
          {
            do
              ++v4;
            while ( lpsz[v4] );
          }
          else
          {
            v4 = 0;
          }
        }
        v5 = v4;
        if ( v4 == -1 )
        {
          if ( lpsz )
          {
            do
              ++v4;
            while ( lpsz[v4] );
            v6 = v4;
          }
          else
          {
            LODWORD(v4) = 0;
            v6 = 0;
          }
        }
        else
        {
          v6 = v4;
        }
        if ( v6 )
        {
          if ( v6 == -1 )
          {
            if ( lpsz )
            {
              v4 = -1;
              do
                ++v4;
              while ( lpsz[v4] );
            }
            else
            {
              LODWORD(v4) = 0;
            }
          }
          CharUpperBuffW(lpsz, v4);
          v7 = 0;
          for ( i = 314159269; v7 < 2 * v5; i ^= (i >> 2) + 2080 * i + v9 )
            v9 = *((unsigned __int8 *)v1 + v7++);
          v0 = i & 0x7FFFFFFF;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x60,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\RUPTelemetryHelpers.h",
          (const char *)(unsigned int)v3);
        if ( Buffer )
          NetApiBufferFree(Buffer);
        v1 = lpsz;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\RUPTelemetryHelpers.h",
        (const char *)(unsigned int)DcNameW);
      if ( Buffer )
        NetApiBufferFree(Buffer);
    }
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800043a0  mov     r11, rsp
0x1800043a3  mov     [r11+18h], rbx
0x1800043a7  push    rdi
0x1800043a8  sub     rsp, 50h
0x1800043ac  lea     rax, [r11+8]
0x1800043b0  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFFh
0x1800043b8  mov     [r11-30h], rax
0x1800043bc  xor     ebx, ebx
0x1800043be  xor     edi, edi
0x1800043c0  mov     [rsp+58h+Flags], 40008100h; int
0x1800043c8  xor     r9d, r9d; SiteName
0x1800043cb  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFFh
0x1800043d3  xor     r8d, r8d; DomainGuid
0x1800043d6  mov     [r11-28h], rdi
0x1800043da  xor     edx, edx; DomainName
0x1800043dc  mov     [r11+8], rbx
0x1800043e0  xor     ecx, ecx; ComputerName
0x1800043e2  call    cs:__imp_DsGetDcNameW
0x1800043e8  test    eax, eax
0x1800043ea  jle     short loc_1800043F4
0x1800043ec  movzx   eax, ax
0x1800043ef  or      eax, 80070000h
0x1800043f4  cmp     eax, 8007054Bh
0x1800043f9  jnz     short loc_180004414
0x1800043fb  mov     rcx, [rsp+58h+Buffer]; Buffer
0x180004400  test    rcx, rcx
0x180004403  jz      loc_18000456F
0x180004409  call    cs:__imp_NetApiBufferFree
0x18000440f  jmp     loc_18000456F
0x180004414  test    eax, eax
0x180004416  jns     short loc_18000444A
0x180004418  mov     rcx, [rsp+58h]; this
0x18000441d  lea     r8, aClientcoreDsSe; "clientcore\\ds\\security\\gina\\profile"...
0x180004424  mov     r9d, eax; char *
0x180004427  mov     edx, 5Eh ; '^'; void *
0x18000442c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004431  mov     rcx, [rsp+58h+Buffer]; Buffer
0x180004436  test    rcx, rcx
0x180004439  jz      loc_180004556
0x18000443f  call    cs:__imp_NetApiBufferFree
0x180004445  jmp     loc_180004556
0x18000444a  mov     rcx, [rsp+58h+Buffer]
0x18000444f  lea     rdx, [rsp+58h+lpsz]; unsigned __int16 **
0x180004454  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180004458  call    ?HeapAllocString@@YAJPEBGPEAPEAG@Z; HeapAllocString(ushort const *,ushort * *)
0x18000445d  test    eax, eax
0x18000445f  jns     short loc_180004494
0x180004461  mov     rcx, [rsp+58h]; this
0x180004466  lea     r8, aClientcoreDsSe; "clientcore\\ds\\security\\gina\\profile"...
0x18000446d  mov     r9d, eax; char *
0x180004470  mov     edx, 60h ; '`'; void *
0x180004475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000447a  mov     rcx, [rsp+58h+Buffer]; Buffer
0x18000447f  test    rcx, rcx
0x180004482  jz      short loc_18000448A
0x180004484  call    cs:__imp_NetApiBufferFree
0x18000448a  mov     rdi, [rsp+58h+lpsz]
0x18000448f  jmp     loc_180004556
0x180004494  mov     rcx, [rsp+58h+Buffer]; Buffer
0x180004499  mov     [rsp+58h+arg_8], rsi
0x18000449e  test    rcx, rcx
0x1800044a1  jz      short loc_1800044A9
0x1800044a3  call    cs:__imp_NetApiBufferFree
0x1800044a9  mov     rdx, [rsp+58h+var_20]
0x1800044ae  mov     rdi, [rsp+58h+lpsz]
0x1800044b3  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800044b7  jnz     short loc_1800044CB
0x1800044b9  test    rdi, rdi
0x1800044bc  jz      short loc_1800044C9
0x1800044be  inc     rdx
0x1800044c1  cmp     [rdi+rdx*2], bx
0x1800044c5  jnz     short loc_1800044BE
0x1800044c7  jmp     short loc_1800044CB
0x1800044c9  xor     edx, edx
0x1800044cb  mov     rsi, rdx
0x1800044ce  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800044d2  jnz     short loc_1800044ED
0x1800044d4  test    rdi, rdi
0x1800044d7  jz      short loc_1800044E7
0x1800044d9  inc     rdx
0x1800044dc  cmp     [rdi+rdx*2], bx
0x1800044e0  jnz     short loc_1800044D9
0x1800044e2  mov     rax, rdx
0x1800044e5  jmp     short loc_1800044F0
0x1800044e7  xor     edx, edx
0x1800044e9  xor     eax, eax
0x1800044eb  jmp     short loc_1800044F0
0x1800044ed  mov     rax, rsi
0x1800044f0  test    rax, rax
0x1800044f3  jz      short loc_180004551
0x1800044f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800044f9  jnz     short loc_180004510
0x1800044fb  test    rdi, rdi
0x1800044fe  jz      short loc_18000450E
0x180004500  mov     rdx, rax
0x180004503  inc     rdx
0x180004506  cmp     [rdi+rdx*2], bx
0x18000450a  jnz     short loc_180004503
0x18000450c  jmp     short loc_180004510
0x18000450e  xor     edx, edx; cchLength
0x180004510  mov     rcx, rdi; lpsz
0x180004513  call    cs:__imp_CharUpperBuffW
0x180004519  lea     r8, [rsi+rsi]
0x18000451d  xor     edx, edx
0x18000451f  mov     ebx, 12B9B0A5h
0x180004524  test    r8, r8
0x180004527  jz      short loc_18000454D
0x180004529  nop     dword ptr [rax+00000000h]
0x180004530  movzx   ecx, byte ptr [rdi+rdx]
0x180004534  inc     rdx
0x180004537  imul    eax, ebx, 820h
0x18000453d  add     ecx, eax
0x18000453f  mov     eax, ebx
0x180004541  shr     eax, 2
0x180004544  add     ecx, eax
0x180004546  xor     ebx, ecx
0x180004548  cmp     rdx, r8
0x18000454b  jb      short loc_180004530
0x18000454d  btr     ebx, 1Fh
0x180004551  mov     rsi, [rsp+58h+arg_8]
0x180004556  test    rdi, rdi
0x180004559  jz      short loc_18000456F
0x18000455b  call    cs:__imp_GetProcessHeap
0x180004561  mov     r8, rdi; lpMem
0x180004564  xor     edx, edx; dwFlags
0x180004566  mov     rcx, rax; hHeap
0x180004569  call    cs:__imp_HeapFree
0x18000456f  mov     eax, ebx
0x180004571  mov     rbx, [rsp+58h+arg_10]
0x180004576  add     rsp, 50h
0x18000457a  pop     rdi
0x18000457b  retn
```
