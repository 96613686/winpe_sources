# CpuUtilizationTroubleshooter::ProcessImageUnloadEvent(_EVENT_RECORD *)

- ea: `0x18001cf70`
- end: `0x18001d2b4`
- name: `?ProcessImageUnloadEvent@CpuUtilizationTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `836`
- prototype: `void(CpuUtilizationTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180019d60`

## callees

- `0x18000f190`
- `0x18001be60`
- `0x18001c8cc`
- `0x18001cbe8`
- `0x18001cf70`
- `0x18003ae80`
- `0x18003bb60`
- `0x18003bf74`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001cfff`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001d04a`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001d095`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001cfff`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001d04a`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001d095`

## string_xrefs

- `0x18001d062`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CpuUtilizationTroubleshooter::ProcessImageUnloadEvent(
        CpuUtilizationTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  __int64 *v4; // rdx
  __int64 *v5; // rax
  __int64 *i; // r14
  __int64 j; // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // r8
  __int64 v14; // rdx
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  _QWORD *v17; // r8
  __int64 v18; // rdx
  BYTE v19[8]; // [rsp+40h] [rbp-29h] BYREF
  BYTE pBuffer[8]; // [rsp+48h] [rbp-21h] BYREF
  BYTE v21[8]; // [rsp+50h] [rbp-19h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+58h] [rbp-11h] BYREF
  wchar_t *S1[2]; // [rsp+70h] [rbp+7h] BYREF
  size_t N; // [rsp+80h] [rbp+17h]
  unsigned __int64 v25; // [rsp+88h] [rbp+1Fh]

  *(_OWORD *)S1 = 0;
  N = 0;
  v25 = 0;
  std::wstring::_Construct_empty(S1);
  *(_QWORD *)pBuffer = 0;
  *(_QWORD *)v21 = 0;
  *(_DWORD *)v19 = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ImageBase";
  if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer) )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"ImageSize";
    if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, v21) )
    {
      pPropertyData.Reserved = 0;
      pPropertyData.ArrayIndex = -1;
      pPropertyData.PropertyName = (ULONGLONG)L"ProcessId";
      if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v19) && !(unsigned int)GetEventProperty(a2) )
      {
        v4 = (__int64 *)*((_QWORD *)this + 9);
        v5 = (__int64 *)v4[1];
        pPropertyData.Reserved = 0;
        for ( i = v4; !*((_BYTE *)v5 + 25); v5 = (__int64 *)*v5 )
        {
          if ( *((_DWORD *)v5 + 7) < *(_DWORD *)v19 )
            v5 += 2;
          else
            i = v5;
        }
        if ( !*((_BYTE *)i + 25) && *(_DWORD *)v19 >= *((_DWORD *)i + 7) && i != v4 )
        {
          for ( j = *((_QWORD *)this + 15); j != *((_QWORD *)this + 16); j += 32 )
          {
            if ( *(_QWORD *)(j + 24) <= 7u )
              v15 = (const wchar_t *)j;
            else
              v15 = *(const wchar_t **)j;
            v16 = (const wchar_t *)S1;
            if ( v25 > 7 )
              v16 = S1[0];
            if ( N == *(_QWORD *)(j + 16) && (!N || !wmemcmp(v16, v15, N)) )
              break;
          }
          v8 = (j - *((_QWORD *)this + 15)) >> 5;
          v9 = *((_QWORD *)this + 16);
          if ( j == v9 )
          {
            if ( v9 == *((_QWORD *)this + 17) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
                (char *)this + 120,
                *((_QWORD *)this + 16),
                S1);
            }
            else
            {
              std::wstring::wstring(*((_QWORD *)this + 16), S1);
              *((_QWORD *)this + 16) += 32LL;
            }
          }
          v10 = *((_QWORD *)this + 6) + 104LL * *((unsigned int *)i + 8);
          v11 = *(_QWORD *)pBuffer;
          v12 = *(_QWORD *)v21;
          v13 = *(_QWORD **)(v10 + 72);
          v14 = *(_QWORD *)(v10 + 80);
          while ( v13 != (_QWORD *)v14 )
          {
            if ( *((_DWORD *)v13 + 4) == (_DWORD)v8 && *v13 == *(_QWORD *)v21 && v13[1] == *(_QWORD *)pBuffer )
            {
              std::_Copy_memmove<OsStateInstance * *,OsStateInstance * *>(v13 + 3, v14, v13);
              *(_QWORD *)(v10 + 80) -= 24LL;
              v11 = *(_QWORD *)pBuffer;
              v12 = *(_QWORD *)v21;
              break;
            }
            v13 += 3;
          }
          if ( !*(_DWORD *)v19 )
          {
            v17 = (_QWORD *)*((_QWORD *)this + 18);
            v18 = *((_QWORD *)this + 19);
            while ( v17 != (_QWORD *)v18 )
            {
              if ( *((_DWORD *)v17 + 4) == (_DWORD)v8 && *v17 == v11 && v17[1] == v12 )
              {
                std::_Copy_memmove<OsStateInstance * *,OsStateInstance * *>(v17 + 3, v18, v17);
                *((_QWORD *)this + 19) -= 24LL;
                break;
              }
              v17 += 3;
            }
          }
        }
      }
    }
  }
  if ( v25 > 7 )
    std::_Deallocate<16>(S1[0], 2 * v25 + 2);
}

```

## disassembly

```asm
0x18001cf70  mov     [rsp-8+arg_10], rbx
0x18001cf75  push    rbp
0x18001cf76  push    rsi
0x18001cf77  push    rdi
0x18001cf78  push    r14
0x18001cf7a  push    r15
0x18001cf7c  lea     rbp, [rsp-37h]
0x18001cf81  sub     rsp, 0A0h
0x18001cf88  mov     rax, cs:__security_cookie
0x18001cf8f  xor     rax, rsp
0x18001cf92  mov     [rbp+57h+var_30], rax
0x18001cf96  mov     rbx, rdx
0x18001cf99  mov     rsi, rcx
0x18001cf9c  xorps   xmm0, xmm0
0x18001cf9f  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18001cfa3  xor     edi, edi
0x18001cfa5  mov     [rbp+57h+N], rdi
0x18001cfa9  mov     [rbp+57h+var_38], rdi
0x18001cfad  lea     rcx, [rbp+57h+S1]
0x18001cfb1  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001cfb6  nop
0x18001cfb7  mov     qword ptr [rbp+57h+var_78], rdi
0x18001cfbb  mov     qword ptr [rbp+57h+var_70], rdi
0x18001cfbf  mov     dword ptr [rbp+57h+var_80], edi
0x18001cfc2  mov     [rbp+57h+var_68.Reserved], edi
0x18001cfc5  mov     [rbp+57h+var_68.ArrayIndex], 0FFFFFFFFh
0x18001cfcc  lea     rax, aImagebase; "ImageBase"
0x18001cfd3  mov     [rbp+57h+var_68.PropertyName], rax
0x18001cfd7  lea     rax, [rbp+57h+var_78]
0x18001cfdb  mov     [rsp+0C0h+pBuffer], rax; pBuffer
0x18001cfe0  mov     [rsp+0C0h+BufferSize], 8; BufferSize
0x18001cfe8  lea     rax, [rbp+57h+var_68]
0x18001cfec  mov     [rsp+0C0h+pPropertyData], rax; pPropertyData
0x18001cff1  mov     r9d, 1; PropertyDataCount
0x18001cff7  xor     r8d, r8d; pTdhContext
0x18001cffa  xor     edx, edx; TdhContextCount
0x18001cffc  mov     rcx, rbx; pEvent
0x18001cfff  call    cs:__imp_TdhGetProperty
0x18001d005  test    eax, eax
0x18001d007  jnz     loc_18001D193
0x18001d00d  mov     [rbp+57h+var_68.Reserved], edi
0x18001d010  mov     [rbp+57h+var_68.ArrayIndex], 0FFFFFFFFh
0x18001d017  lea     rax, aImagesize; "ImageSize"
0x18001d01e  mov     [rbp+57h+var_68.PropertyName], rax
0x18001d022  lea     rax, [rbp+57h+var_70]
0x18001d026  mov     [rsp+0C0h+pBuffer], rax; pBuffer
0x18001d02b  mov     [rsp+0C0h+BufferSize], 8; BufferSize
0x18001d033  lea     rax, [rbp+57h+var_68]
0x18001d037  mov     [rsp+0C0h+pPropertyData], rax; pPropertyData
0x18001d03c  mov     r9d, 1; PropertyDataCount
0x18001d042  xor     r8d, r8d; pTdhContext
0x18001d045  xor     edx, edx; TdhContextCount
0x18001d047  mov     rcx, rbx; pEvent
0x18001d04a  call    cs:__imp_TdhGetProperty
0x18001d050  test    eax, eax
0x18001d052  jnz     loc_18001D193
0x18001d058  mov     [rbp+57h+var_68.Reserved], edi
0x18001d05b  mov     [rbp+57h+var_68.ArrayIndex], 0FFFFFFFFh
0x18001d062  lea     rax, aProcessid; "ProcessId"
0x18001d069  mov     [rbp+57h+var_68.PropertyName], rax
0x18001d06d  lea     rax, [rbp+57h+var_80]
0x18001d071  mov     [rsp+0C0h+pBuffer], rax; pBuffer
0x18001d076  mov     [rsp+0C0h+BufferSize], 4; BufferSize
0x18001d07e  lea     rax, [rbp+57h+var_68]
0x18001d082  mov     [rsp+0C0h+pPropertyData], rax; pPropertyData
0x18001d087  mov     r9d, 1; PropertyDataCount
0x18001d08d  xor     r8d, r8d; pTdhContext
0x18001d090  xor     edx, edx; TdhContextCount
0x18001d092  mov     rcx, rbx; pEvent
0x18001d095  call    cs:__imp_TdhGetProperty
0x18001d09b  test    eax, eax
0x18001d09d  jnz     loc_18001D193
0x18001d0a3  xor     r9d, r9d
0x18001d0a6  lea     r8, [rbp+57h+S1]
0x18001d0aa  lea     rdx, aFilename; "FileName"
0x18001d0b1  mov     rcx, rbx; pEvent
0x18001d0b4  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18001d0b9  test    eax, eax
0x18001d0bb  jnz     loc_18001D193
0x18001d0c1  mov     rdx, [rsi+48h]
0x18001d0c5  mov     rax, [rdx+8]
0x18001d0c9  xor     ecx, ecx
0x18001d0cb  mov     [rbp+57h+var_68.Reserved], ecx
0x18001d0ce  mov     r14, rdx
0x18001d0d1  mov     ecx, dword ptr [rbp+57h+var_80]
0x18001d0d4  cmp     [rax+19h], dil
0x18001d0d8  jnz     short loc_18001D0EF
0x18001d0da  cmp     [rax+1Ch], ecx
0x18001d0dd  jb      loc_18001D16A
0x18001d0e3  mov     r14, rax
0x18001d0e6  mov     rax, [rax]
0x18001d0e9  cmp     byte ptr [rax+19h], 0
0x18001d0ed  jz      short loc_18001D0DA
0x18001d0ef  cmp     byte ptr [r14+19h], 0
0x18001d0f4  jnz     loc_18001D193
0x18001d0fa  cmp     ecx, [r14+1Ch]
0x18001d0fe  jb      loc_18001D193
0x18001d104  cmp     r14, rdx
0x18001d107  jz      loc_18001D193
0x18001d10d  mov     rbx, [rsi+78h]
0x18001d111  cmp     rbx, [rsi+80h]
0x18001d118  jnz     loc_18001D1C4
0x18001d11e  mov     rdi, rbx
0x18001d121  sub     rdi, [rsi+78h]
0x18001d125  sar     rdi, 5
0x18001d129  mov     rax, [rsi+80h]
0x18001d130  cmp     rbx, rax
0x18001d133  jz      loc_18001D223
0x18001d139  mov     eax, [r14+20h]
0x18001d13d  imul    rbx, rax, 68h ; 'h'
0x18001d141  add     rbx, [rsi+30h]
0x18001d145  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001d149  mov     rax, qword ptr [rbp+57h+var_70]
0x18001d14d  mov     r8, [rbx+48h]
0x18001d151  mov     rdx, [rbx+50h]
0x18001d155  cmp     r8, rdx
0x18001d158  jz      short loc_18001D189
0x18001d15a  cmp     [r8+10h], edi
0x18001d15e  jz      loc_18001D1F4
0x18001d164  add     r8, 18h
0x18001d168  jmp     short loc_18001D155
0x18001d16a  add     rax, 10h
0x18001d16e  jmp     loc_18001D0E6
0x18001d173  lea     rcx, [r8+18h]; Src
0x18001d177  call    ??$_Copy_memmove@PEAPEAVOsStateInstance@@PEAPEAV1@@std@@YAPEAPEAVOsStateInstance@@PEAPEAV1@00@Z; std::_Copy_memmove<OsStateInstance * *,OsStateInstance * *>(OsStateInstance * *,OsStateInstance * *,OsStateInstance * *)
0x18001d17c  add     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFE8h
0x18001d181  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001d185  mov     rax, qword ptr [rbp+57h+var_70]
0x18001d189  cmp     dword ptr [rbp+57h+var_80], 0
0x18001d18d  jz      loc_18001D245
0x18001d193  mov     rdx, [rbp+57h+var_38]
0x18001d197  cmp     rdx, 7
0x18001d19b  ja      loc_18001D29E
0x18001d1a1  mov     rcx, [rbp+57h+var_30]
0x18001d1a5  xor     rcx, rsp; StackCookie
0x18001d1a8  call    __security_check_cookie
0x18001d1ad  mov     rbx, [rsp+0C0h+arg_10]
0x18001d1b5  add     rsp, 0A0h
0x18001d1bc  pop     r15
0x18001d1be  pop     r14
0x18001d1c0  pop     rdi
0x18001d1c1  pop     rsi
0x18001d1c2  pop     rbp
0x18001d1c3  retn
0x18001d1c4  cmp     qword ptr [rbx+18h], 7
0x18001d1c9  jbe     short loc_18001D1EF
0x18001d1cb  mov     rdx, [rbx]; S2
0x18001d1ce  mov     r8, [rbp+57h+N]; N
0x18001d1d2  lea     rcx, [rbp+57h+S1]
0x18001d1d6  cmp     [rbp+57h+var_38], 7
0x18001d1db  cmova   rcx, [rbp+57h+S1]; S1
0x18001d1e0  cmp     r8, [rbx+10h]
0x18001d1e4  jz      short loc_18001D20C
0x18001d1e6  add     rbx, 20h ; ' '
0x18001d1ea  jmp     loc_18001D111
0x18001d1ef  mov     rdx, rbx
0x18001d1f2  jmp     short loc_18001D1CE
0x18001d1f4  cmp     [r8], rax
0x18001d1f7  jnz     loc_18001D164
0x18001d1fd  cmp     [r8+8], rcx
0x18001d201  jnz     loc_18001D164
0x18001d207  jmp     loc_18001D173
0x18001d20c  test    r8, r8
0x18001d20f  jz      loc_18001D11E
0x18001d215  call    wmemcmp
0x18001d21a  test    eax, eax
0x18001d21c  jnz     short loc_18001D1E6
0x18001d21e  jmp     loc_18001D11E
0x18001d223  cmp     rax, [rsi+88h]
0x18001d22a  jz      short loc_18001D289
0x18001d22c  lea     rdx, [rbp+57h+S1]
0x18001d230  mov     rcx, rax
0x18001d233  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d238  add     qword ptr [rsi+80h], 20h ; ' '
0x18001d240  jmp     loc_18001D139
0x18001d245  mov     r8, [rsi+90h]
0x18001d24c  mov     rdx, [rsi+98h]
0x18001d253  cmp     r8, rdx
0x18001d256  jz      loc_18001D193
0x18001d25c  cmp     [r8+10h], edi
0x18001d260  jnz     short loc_18001D283
0x18001d262  cmp     [r8], rcx
0x18001d265  jnz     short loc_18001D283
0x18001d267  cmp     [r8+8], rax
0x18001d26b  jnz     short loc_18001D283
0x18001d26d  lea     rcx, [r8+18h]; Src
0x18001d271  call    ??$_Copy_memmove@PEAPEAVOsStateInstance@@PEAPEAV1@@std@@YAPEAPEAVOsStateInstance@@PEAPEAV1@00@Z; std::_Copy_memmove<OsStateInstance * *,OsStateInstance * *>(OsStateInstance * *,OsStateInstance * *,OsStateInstance * *)
0x18001d276  add     qword ptr [rsi+98h], 0FFFFFFFFFFFFFFE8h
0x18001d27e  jmp     loc_18001D193
0x18001d283  add     r8, 18h
0x18001d287  jmp     short loc_18001D253
0x18001d289  lea     r8, [rbp+57h+S1]
0x18001d28d  mov     rdx, rax
0x18001d290  lea     rcx, [rsi+78h]
0x18001d294  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001d299  jmp     loc_18001D139
0x18001d29e  lea     rdx, ds:2[rdx*2]
0x18001d2a6  mov     rcx, [rbp+57h+S1]
0x18001d2aa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d2af  jmp     loc_18001D1A1
```
