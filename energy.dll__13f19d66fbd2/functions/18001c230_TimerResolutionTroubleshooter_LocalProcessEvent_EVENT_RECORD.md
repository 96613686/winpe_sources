# TimerResolutionTroubleshooter::LocalProcessEvent(_EVENT_RECORD *)

- ea: `0x18001c230`
- end: `0x18001c8c3`
- name: `?LocalProcessEvent@TimerResolutionTroubleshooter@@MEAAXPEAU_EVENT_RECORD@@@Z`
- size: `1683`
- prototype: `void __fastcall(TimerResolutionTroubleshooter *__hidden this, PEVENT_RECORD pEvent)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180004e20`
- `0x18001be60`
- `0x18001c230`
- `0x18001c8cc`
- `0x18001c910`
- `0x18001c968`
- `0x18001ca04`
- `0x18001cbe8`
- `0x18001ccf4`
- `0x1800209ec`
- `0x180027f10`
- `0x18002e9b4`
- `0x18003ae80`
- `0x18003bb60`
- `0x18003bbfc`
- `0x18003bf74`
- `0x18003bf8c`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c33f`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c38b`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c3d7`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c670`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c6c1`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c33f`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c38b`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c3d7`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c670`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c6c1`

## string_xrefs

- `0x18001c3a3`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TimerResolutionTroubleshooter::LocalProcessEvent(
        TimerResolutionTroubleshooter *this,
        PEVENT_RECORD pEvent)
{
  int v4; // ecx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 *v8; // rdx
  __int64 *v9; // rax
  __int64 *i; // r14
  __int64 j; // rbx
  const wchar_t *v12; // rdx
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  USHORT Id; // ax
  __int64 v18; // rsi
  __int64 v19; // rax
  TDHSTATUS Property; // eax
  void *v21; // r14
  wchar_t **v22; // rdx
  __int64 v23; // rax
  BYTE v24[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE pBuffer[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h]
  BYTE v28[8]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *S1[2]; // [rsp+B8h] [rbp-48h] BYREF
  size_t N; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v37; // [rsp+D0h] [rbp-30h]
  _BYTE v38[96]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = *((_DWORD *)this + 40);
  if ( (v4 & 0x20) == 0 )
  {
    v5 = *(_QWORD *)&pEvent->EventHeader.ProviderId.Data1 - POP_ETW_PROVIDER;
    if ( !v5 )
      v5 = *(_QWORD *)pEvent->EventHeader.ProviderId.Data4 - *((_QWORD *)&POP_ETW_PROVIDER + 1);
    if ( v5 )
    {
      v6 = *(_QWORD *)&pEvent->EventHeader.ProviderId.Data1 - *(_QWORD *)&ENERGY_ETW_PROVIDER.Data1;
      if ( !v6 )
        v6 = *(_QWORD *)pEvent->EventHeader.ProviderId.Data4 - *(_QWORD *)ENERGY_ETW_PROVIDER.Data4;
      if ( v6 )
      {
        v7 = *(_QWORD *)&pEvent->EventHeader.ProviderId.Data1 - ImageLoadGuid;
        if ( !v7 )
          v7 = *(_QWORD *)pEvent->EventHeader.ProviderId.Data4 - 0x18F511C9A000E1ABLL;
        if ( !v7 )
        {
          if ( pEvent->EventHeader.EventDescriptor.Opcode != 3 )
            return;
          *(_OWORD *)S1 = 0;
          N = 0;
          v37 = 0;
          std::wstring::_Construct_empty(S1);
          *(_QWORD *)pBuffer = 0;
          *(_QWORD *)v28 = 0;
          *(_DWORD *)v24 = 0;
          pPropertyData.Reserved = 0;
          pPropertyData.ArrayIndex = -1;
          pPropertyData.PropertyName = (ULONGLONG)L"ImageBase";
          if ( !TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 8u, pBuffer) )
          {
            pPropertyData.Reserved = 0;
            pPropertyData.ArrayIndex = -1;
            pPropertyData.PropertyName = (ULONGLONG)L"ImageSize";
            if ( !TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 8u, v28) )
            {
              pPropertyData.Reserved = 0;
              pPropertyData.ArrayIndex = -1;
              pPropertyData.PropertyName = (ULONGLONG)L"ProcessId";
              if ( !TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 4u, v24) && !(unsigned int)GetEventProperty(pEvent) )
              {
                v8 = (__int64 *)*((_QWORD *)this + 12);
                v9 = (__int64 *)v8[1];
                HIDWORD(v29) = 0;
                for ( i = v8; !*((_BYTE *)v9 + 25); v9 = (__int64 *)*v9 )
                {
                  if ( *((_DWORD *)v9 + 8) >= *(_DWORD *)v24 )
                    i = v9;
                  else
                    v9 += 2;
                }
                if ( !*((_BYTE *)i + 25) && *(_DWORD *)v24 >= *((_DWORD *)i + 8) && i != v8 )
                {
                  for ( j = *((_QWORD *)this + 14); j != *((_QWORD *)this + 15); j += 32 )
                  {
                    if ( *(_QWORD *)(j + 24) <= 7u )
                      v12 = (const wchar_t *)j;
                    else
                      v12 = *(const wchar_t **)j;
                    v13 = (const wchar_t *)S1;
                    if ( v37 > 7 )
                      v13 = S1[0];
                    if ( N == *(_QWORD *)(j + 16) && (!N || !wmemcmp(v13, v12, N)) )
                      break;
                  }
                  v18 = (j - *((_QWORD *)this + 14)) >> 5;
                  v19 = *((_QWORD *)this + 15);
                  if ( j == v19 )
                  {
                    if ( v19 == *((_QWORD *)this + 16) )
                    {
                      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
                        (char *)this + 112,
                        *((_QWORD *)this + 15),
                        S1);
                    }
                    else
                    {
                      std::wstring::wstring(*((_QWORD *)this + 15), S1);
                      *((_QWORD *)this + 15) += 32LL;
                    }
                  }
                  *(_QWORD *)&v26 = *(_QWORD *)pBuffer;
                  *((_QWORD *)&v26 + 1) = *(_QWORD *)v28;
                  LODWORD(v27) = v18;
                  v14 = i[6];
                  if ( v14 == i[7] )
                  {
                    std::vector<ImageMapping>::_Emplace_reallocate<ImageMapping>(i + 5, v14, &v26);
                  }
                  else
                  {
                    *(_OWORD *)v14 = v26;
                    *(_QWORD *)(v14 + 16) = v27;
                    i[6] += 24;
                  }
                  if ( !*(_DWORD *)v24 )
                  {
                    *(_QWORD *)&v26 = *(_QWORD *)pBuffer;
                    *((_QWORD *)&v26 + 1) = *(_QWORD *)v28;
                    LODWORD(v27) = v18;
                    v15 = *((_QWORD *)this + 18);
                    if ( v15 == *((_QWORD *)this + 19) )
                    {
                      std::vector<ImageMapping>::_Emplace_reallocate<ImageMapping>((char *)this + 136, v15, &v26);
                    }
                    else
                    {
                      *(_OWORD *)v15 = v26;
                      *(_QWORD *)(v15 + 16) = v27;
                      *((_QWORD *)this + 18) += 24LL;
                    }
                  }
                  *((_DWORD *)this + 40) |= 0x40u;
                }
              }
            }
          }
          goto LABEL_40;
        }
        v16 = *(_QWORD *)&pEvent->EventHeader.ProviderId.Data1 - ProcessGuid;
        if ( !v16 )
          v16 = *(_QWORD *)pEvent->EventHeader.ProviderId.Data4 - 0x7CBAD74FC000DA9DLL;
        if ( !v16 && pEvent->EventHeader.EventDescriptor.Opcode == 3 )
          TimerResolutionTroubleshooter::ProcessProcessStartEvent(this, pEvent);
      }
      else if ( pEvent->EventHeader.EventDescriptor.Id == 3 )
      {
        *((_DWORD *)this + 40) = v4 | 0x20;
      }
    }
    else
    {
      Id = pEvent->EventHeader.EventDescriptor.Id;
      switch ( Id )
      {
        case 'a':
          *(_OWORD *)S1 = 0;
          N = 0;
          v37 = 0;
          std::wstring::_Construct_empty(S1);
          *(_DWORD *)pBuffer = 0;
          *(_DWORD *)v24 = 0;
          std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&v26);
          pPropertyData.Reserved = 0;
          pPropertyData.ArrayIndex = -1;
          pPropertyData.PropertyName = (ULONGLONG)L"RequestedPeriod";
          Property = TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 4u, pBuffer);
          v21 = (void *)v26;
          if ( !Property )
          {
            pPropertyData.Reserved = 0;
            pPropertyData.ArrayIndex = -1;
            pPropertyData.PropertyName = (ULONGLONG)L"Pid";
            if ( !TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 4u, v24) && !(unsigned int)GetEventProperty(pEvent) )
            {
              *(_QWORD *)v28 = &v29;
              v29 = 0;
              v30 = 0;
              std::vector<unsigned __int64>::_Construct_n<unsigned __int64 * const &,unsigned __int64 * const &>(
                &v29,
                (__int64)(*((_QWORD *)&v26 + 1) - (_QWORD)v21) >> 3,
                &v26,
                (char *)&v26 + 8);
              v31 = 0;
              v32 = 0;
              v33 = 0;
              v22 = S1;
              if ( v37 > 7 )
                v22 = (wchar_t **)S1[0];
              std::wstring::_Construct<2,unsigned short const *>(&v31, v22, N);
              v23 = TimerResolutionRequest::TimerResolutionRequest(
                      v38,
                      *(unsigned int *)pBuffer,
                      *(unsigned int *)v24,
                      &v31,
                      &v29);
              std::vector<TimerResolutionRequest>::push_back((char *)this + 48, v23);
              TimerResolutionRequest::~TimerResolutionRequest((TimerResolutionRequest *)v38);
            }
          }
          if ( v21 )
            std::_Deallocate<16>(v21, (v27 - (_QWORD)v21) & 0xFFFFFFFFFFFFFFF8uLL);
LABEL_40:
          if ( v37 > 7 )
            std::_Deallocate<16>(S1[0], 2 * v37 + 2);
          return;
        case '`':
          if ( *((_BYTE *)this + 24) )
          {
            *((_DWORD *)this + 2) = 3;
          }
          else
          {
            *((_BYTE *)this + 24) = 1;
            if ( !GetEventProperty(pEvent, L"CurrentPeriod", (unsigned int *)this + 7) )
              *((_DWORD *)this + 40) |= 1u;
            if ( !GetEventProperty(pEvent, L"MinimumPeriod", (unsigned int *)this + 8) )
              *((_DWORD *)this + 40) |= 2u;
            if ( !GetEventProperty(pEvent, L"MaximumPeriod", (unsigned int *)this + 9) )
              *((_DWORD *)this + 40) |= 4u;
            if ( !GetEventProperty(pEvent, L"KernelRequestCount", (unsigned int *)this + 10) )
              *((_DWORD *)this + 40) |= 8u;
            if ( !GetEventProperty(pEvent, L"KernelRequestedPeriod", (unsigned int *)this + 11) )
              *((_DWORD *)this + 40) |= 0x10u;
          }
          break;
        case 'n':
          TimerResolutionTroubleshooter::ProcessTimerResolutionStackRundownEvent(this, pEvent);
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x18001c230  mov     [rsp-8+arg_10], rbx
0x18001c235  push    rbp
0x18001c236  push    rsi
0x18001c237  push    rdi
0x18001c238  push    r14
0x18001c23a  push    r15
0x18001c23c  lea     rbp, [rsp-50h]
0x18001c241  sub     rsp, 150h
0x18001c248  mov     rax, cs:__security_cookie
0x18001c24f  xor     rax, rsp
0x18001c252  mov     [rbp+70h+var_30], rax
0x18001c256  mov     rbx, rdx
0x18001c259  mov     rdi, rcx
0x18001c25c  mov     ecx, [rcx+0A0h]
0x18001c262  test    cl, 20h
0x18001c265  jnz     loc_18001C554
0x18001c26b  mov     rax, [rdx+18h]
0x18001c26f  sub     rax, qword ptr cs:POP_ETW_PROVIDER
0x18001c276  jnz     short loc_18001C283
0x18001c278  mov     rax, [rdx+20h]
0x18001c27c  sub     rax, qword ptr cs:POP_ETW_PROVIDER+8
0x18001c283  test    rax, rax
0x18001c286  jz      loc_18001C5A4
0x18001c28c  mov     rax, [rdx+18h]
0x18001c290  sub     rax, qword ptr cs:ENERGY_ETW_PROVIDER.Data1
0x18001c297  jnz     short loc_18001C2A4
0x18001c299  mov     rax, [rdx+20h]
0x18001c29d  sub     rax, qword ptr cs:ENERGY_ETW_PROVIDER.Data4
0x18001c2a4  test    rax, rax
0x18001c2a7  jz      loc_18001C7F1
0x18001c2ad  mov     rax, [rdx+18h]
0x18001c2b1  sub     rax, cs:ImageLoadGuid
0x18001c2b8  jnz     short loc_18001C2C5
0x18001c2ba  mov     rax, [rdx+20h]
0x18001c2be  sub     rax, cs:qword_18009C8F0
0x18001c2c5  test    rax, rax
0x18001c2c8  jnz     loc_18001C577
0x18001c2ce  cmp     byte ptr [rdx+2Dh], 3
0x18001c2d2  jnz     loc_18001C554
0x18001c2d8  xorps   xmm0, xmm0
0x18001c2db  movups  xmmword ptr [rbp+70h+S1], xmm0
0x18001c2df  xor     esi, esi
0x18001c2e1  mov     [rbp+70h+N], rsi
0x18001c2e5  mov     [rbp+70h+var_A0], rsi
0x18001c2e9  lea     rcx, [rbp+70h+S1]
0x18001c2ed  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001c2f2  nop
0x18001c2f3  mov     qword ptr [rsp+170h+var_128], rsi
0x18001c2f8  mov     qword ptr [rsp+170h+var_108], rsi
0x18001c2fd  mov     dword ptr [rsp+170h+var_130], esi
0x18001c301  mov     [rbp+70h+var_C8.Reserved], esi
0x18001c304  mov     [rbp+70h+var_C8.ArrayIndex], 0FFFFFFFFh
0x18001c30b  lea     rax, aImagebase; "ImageBase"
0x18001c312  mov     [rbp+70h+var_C8.PropertyName], rax
0x18001c316  lea     rax, [rsp+170h+var_128]
0x18001c31b  mov     [rsp+170h+pBuffer], rax; pBuffer
0x18001c320  mov     [rsp+170h+BufferSize], 8; BufferSize
0x18001c328  lea     rax, [rbp+70h+var_C8]
0x18001c32c  mov     [rsp+170h+pPropertyData], rax; pPropertyData
0x18001c331  mov     r9d, 1; PropertyDataCount
0x18001c337  xor     r8d, r8d; pTdhContext
0x18001c33a  xor     edx, edx; TdhContextCount
0x18001c33c  mov     rcx, rbx; pEvent
0x18001c33f  call    cs:__imp_TdhGetProperty
0x18001c345  test    eax, eax
0x18001c347  jnz     loc_18001C546
0x18001c34d  mov     [rbp+70h+var_C8.Reserved], esi
0x18001c350  mov     [rbp+70h+var_C8.ArrayIndex], 0FFFFFFFFh
0x18001c357  lea     rax, aImagesize; "ImageSize"
0x18001c35e  mov     [rbp+70h+var_C8.PropertyName], rax
0x18001c362  lea     rax, [rsp+170h+var_108]
0x18001c367  mov     [rsp+170h+pBuffer], rax; pBuffer
0x18001c36c  mov     [rsp+170h+BufferSize], 8; BufferSize
0x18001c374  lea     rax, [rbp+70h+var_C8]
0x18001c378  mov     [rsp+170h+pPropertyData], rax; pPropertyData
0x18001c37d  mov     r9d, 1; PropertyDataCount
0x18001c383  xor     r8d, r8d; pTdhContext
0x18001c386  xor     edx, edx; TdhContextCount
0x18001c388  mov     rcx, rbx; pEvent
0x18001c38b  call    cs:__imp_TdhGetProperty
0x18001c391  test    eax, eax
0x18001c393  jnz     loc_18001C546
0x18001c399  mov     [rbp+70h+var_C8.Reserved], esi
0x18001c39c  mov     [rbp+70h+var_C8.ArrayIndex], 0FFFFFFFFh
0x18001c3a3  lea     rax, aProcessid; "ProcessId"
0x18001c3aa  mov     [rbp+70h+var_C8.PropertyName], rax
0x18001c3ae  lea     rax, [rsp+170h+var_130]
0x18001c3b3  mov     [rsp+170h+pBuffer], rax; pBuffer
0x18001c3b8  mov     [rsp+170h+BufferSize], 4; BufferSize
0x18001c3c0  lea     rax, [rbp+70h+var_C8]
0x18001c3c4  mov     [rsp+170h+pPropertyData], rax; pPropertyData
0x18001c3c9  mov     r9d, 1; PropertyDataCount
0x18001c3cf  xor     r8d, r8d; pTdhContext
0x18001c3d2  xor     edx, edx; TdhContextCount
0x18001c3d4  mov     rcx, rbx; pEvent
0x18001c3d7  call    cs:__imp_TdhGetProperty
0x18001c3dd  test    eax, eax
0x18001c3df  jnz     loc_18001C546
0x18001c3e5  xor     r9d, r9d
0x18001c3e8  lea     r8, [rbp+70h+S1]
0x18001c3ec  lea     rdx, aFilename; "FileName"
0x18001c3f3  mov     rcx, rbx; pEvent
0x18001c3f6  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18001c3fb  test    eax, eax
0x18001c3fd  jnz     loc_18001C546
0x18001c403  mov     rdx, [rdi+60h]
0x18001c407  mov     rax, [rdx+8]
0x18001c40b  xor     ecx, ecx
0x18001c40d  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x18001c411  mov     r14, rdx
0x18001c414  mov     ecx, dword ptr [rsp+170h+var_130]
0x18001c418  cmp     [rax+19h], sil
0x18001c41c  jnz     short loc_18001C432
0x18001c41e  xchg    ax, ax
0x18001c420  cmp     [rax+20h], ecx
0x18001c423  jnb     short loc_18001C48E
0x18001c425  add     rax, 10h
0x18001c429  mov     rax, [rax]
0x18001c42c  cmp     byte ptr [rax+19h], 0
0x18001c430  jz      short loc_18001C420
0x18001c432  cmp     byte ptr [r14+19h], 0
0x18001c437  jnz     loc_18001C546
0x18001c43d  cmp     ecx, [r14+20h]
0x18001c441  jb      loc_18001C546
0x18001c447  cmp     r14, rdx
0x18001c44a  jz      loc_18001C546
0x18001c450  mov     rbx, [rdi+70h]
0x18001c454  cmp     rbx, [rdi+78h]
0x18001c458  jz      loc_18001C5CB
0x18001c45e  cmp     qword ptr [rbx+18h], 7
0x18001c463  jbe     loc_18001C5E8
0x18001c469  mov     rdx, [rbx]; S2
0x18001c46c  mov     r8, [rbp+70h+N]; N
0x18001c470  lea     rcx, [rbp+70h+S1]
0x18001c474  cmp     [rbp+70h+var_A0], 7
0x18001c479  cmova   rcx, [rbp+70h+S1]; S1
0x18001c47e  cmp     r8, [rbx+10h]
0x18001c482  jz      loc_18001C5F0
0x18001c488  add     rbx, 20h ; ' '
0x18001c48c  jmp     short loc_18001C454
0x18001c48e  mov     r14, rax
0x18001c491  jmp     short loc_18001C429
0x18001c493  cmp     rax, [rdi+80h]
0x18001c49a  jz      loc_18001C7A7
0x18001c4a0  lea     rdx, [rbp+70h+S1]
0x18001c4a4  mov     rcx, rax
0x18001c4a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c4ac  add     qword ptr [rdi+78h], 20h ; ' '
0x18001c4b1  lea     rcx, [r14+28h]
0x18001c4b5  mov     rax, qword ptr [rsp+170h+var_128]
0x18001c4ba  mov     qword ptr [rsp+170h+var_120], rax
0x18001c4bf  mov     rax, qword ptr [rsp+170h+var_108]
0x18001c4c4  mov     qword ptr [rsp+170h+var_120+8], rax
0x18001c4c9  mov     dword ptr [rsp+170h+var_110], esi
0x18001c4cd  mov     rdx, [rcx+8]
0x18001c4d1  cmp     rdx, [rcx+10h]
0x18001c4d5  jz      loc_18001C7BC
0x18001c4db  movups  xmm0, [rsp+170h+var_120]
0x18001c4e0  movups  xmmword ptr [rdx], xmm0
0x18001c4e3  movsd   xmm1, [rsp+170h+var_110]
0x18001c4e9  movsd   qword ptr [rdx+10h], xmm1
0x18001c4ee  add     qword ptr [rcx+8], 18h
0x18001c4f3  cmp     dword ptr [rsp+170h+var_130], 0
0x18001c4f8  jnz     short loc_18001C53F
0x18001c4fa  lea     rcx, [rdi+88h]
0x18001c501  mov     rax, qword ptr [rsp+170h+var_128]
0x18001c506  mov     qword ptr [rsp+170h+var_120], rax
0x18001c50b  mov     rax, qword ptr [rsp+170h+var_108]
0x18001c510  mov     qword ptr [rsp+170h+var_120+8], rax
0x18001c515  mov     dword ptr [rsp+170h+var_110], esi
0x18001c519  mov     rdx, [rcx+8]
0x18001c51d  cmp     rdx, [rcx+10h]
0x18001c521  jz      loc_18001C7CB
0x18001c527  movups  xmm0, [rsp+170h+var_120]
0x18001c52c  movups  xmmword ptr [rdx], xmm0
0x18001c52f  movsd   xmm1, [rsp+170h+var_110]
0x18001c535  movsd   qword ptr [rdx+10h], xmm1
0x18001c53a  add     qword ptr [rcx+8], 18h
0x18001c53f  or      dword ptr [rdi+0A0h], 40h
0x18001c546  mov     rdx, [rbp+70h+var_A0]
0x18001c54a  cmp     rdx, 7
0x18001c54e  ja      loc_18001C8AD
0x18001c554  mov     rcx, [rbp+70h+var_30]
0x18001c558  xor     rcx, rsp; StackCookie
0x18001c55b  call    __security_check_cookie
0x18001c560  mov     rbx, [rsp+170h+arg_10]
0x18001c568  add     rsp, 150h
0x18001c56f  pop     r15
0x18001c571  pop     r14
0x18001c573  pop     rdi
0x18001c574  pop     rsi
0x18001c575  pop     rbp
0x18001c576  retn
0x18001c577  mov     rax, [rdx+18h]
0x18001c57b  sub     rax, cs:ProcessGuid
0x18001c582  jnz     short loc_18001C58F
0x18001c584  mov     rax, [rdx+20h]
0x18001c588  sub     rax, cs:qword_18009C980
0x18001c58f  test    rax, rax
0x18001c592  jnz     short loc_18001C554
0x18001c594  cmp     byte ptr [rdx+2Dh], 3
0x18001c598  jnz     short loc_18001C554
0x18001c59a  mov     rcx, rdi; this
0x18001c59d  call    ?ProcessProcessStartEvent@TimerResolutionTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z; TimerResolutionTroubleshooter::ProcessProcessStartEvent(_EVENT_RECORD *)
0x18001c5a2  jmp     short loc_18001C554
0x18001c5a4  movzx   eax, word ptr [rdx+28h]
0x18001c5a8  cmp     ax, 61h ; 'a'
0x18001c5ac  jz      short loc_18001C604
0x18001c5ae  cmp     ax, 60h ; '`'
0x18001c5b2  jnz     loc_18001C7DA
0x18001c5b8  cmp     byte ptr [rdi+18h], 0
0x18001c5bc  jz      loc_18001C80A
0x18001c5c2  mov     dword ptr [rdi+8], 3
0x18001c5c9  jmp     short loc_18001C554
0x18001c5cb  mov     rsi, rbx
0x18001c5ce  sub     rsi, [rdi+70h]
0x18001c5d2  sar     rsi, 5
0x18001c5d6  mov     rax, [rdi+78h]
0x18001c5da  cmp     rbx, rax
0x18001c5dd  jz      loc_18001C493
0x18001c5e3  jmp     loc_18001C4B1
0x18001c5e8  mov     rdx, rbx
0x18001c5eb  jmp     loc_18001C46C
0x18001c5f0  test    r8, r8
0x18001c5f3  jz      short loc_18001C5CB
0x18001c5f5  call    wmemcmp
0x18001c5fa  test    eax, eax
0x18001c5fc  jnz     loc_18001C488
0x18001c602  jmp     short loc_18001C5CB
0x18001c604  xorps   xmm0, xmm0
0x18001c607  movups  xmmword ptr [rbp+70h+S1], xmm0
0x18001c60b  xor     esi, esi
0x18001c60d  mov     [rbp+70h+N], rsi
0x18001c611  mov     [rbp+70h+var_A0], rsi
0x18001c615  lea     rcx, [rbp+70h+S1]
0x18001c619  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001c61e  nop
0x18001c61f  mov     dword ptr [rsp+170h+var_128], esi
0x18001c623  mov     dword ptr [rsp+170h+var_130], esi
0x18001c627  lea     rcx, [rsp+170h+var_120]; void *
0x18001c62c  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x18001c631  nop
0x18001c632  mov     [rbp+70h+var_C8.Reserved], esi
0x18001c635  mov     [rbp+70h+var_C8.ArrayIndex], 0FFFFFFFFh
0x18001c63c  lea     rax, aRequestedperio; "RequestedPeriod"
0x18001c643  mov     [rbp+70h+var_C8.PropertyName], rax
0x18001c647  lea     rax, [rsp+170h+var_128]
0x18001c64c  mov     [rsp+170h+pBuffer], rax; pBuffer
0x18001c651  mov     [rsp+170h+BufferSize], 4; BufferSize
0x18001c659  lea     rax, [rbp+70h+var_C8]
0x18001c65d  mov     [rsp+170h+pPropertyData], rax; pPropertyData
0x18001c662  mov     r9d, 1; PropertyDataCount
0x18001c668  xor     r8d, r8d; pTdhContext
0x18001c66b  xor     edx, edx; TdhContextCount
0x18001c66d  mov     rcx, rbx; pEvent
0x18001c670  call    cs:__imp_TdhGetProperty
0x18001c676  mov     r14, qword ptr [rsp+170h+var_120]
0x18001c67b  test    eax, eax
0x18001c67d  jnz     loc_18001C788
0x18001c683  mov     [rbp+70h+var_C8.Reserved], esi
0x18001c686  mov     [rbp+70h+var_C8.ArrayIndex], 0FFFFFFFFh
0x18001c68d  lea     rax, aPid; "Pid"
0x18001c694  mov     [rbp+70h+var_C8.PropertyName], rax
0x18001c698  lea     rax, [rsp+170h+var_130]
0x18001c69d  mov     [rsp+170h+pBuffer], rax; pBuffer
0x18001c6a2  mov     [rsp+170h+BufferSize], 4; BufferSize
0x18001c6aa  lea     rax, [rbp+70h+var_C8]
0x18001c6ae  mov     [rsp+170h+pPropertyData], rax; pPropertyData
0x18001c6b3  mov     r9d, 1; PropertyDataCount
0x18001c6b9  xor     r8d, r8d; pTdhContext
0x18001c6bc  xor     edx, edx; TdhContextCount
0x18001c6be  mov     rcx, rbx; pEvent
0x18001c6c1  call    cs:__imp_TdhGetProperty
0x18001c6c7  test    eax, eax
0x18001c6c9  jnz     loc_18001C788
0x18001c6cf  xor     r9d, r9d
0x18001c6d2  lea     r8, [rbp+70h+S1]
0x18001c6d6  lea     rdx, aAppname; "AppName"
0x18001c6dd  mov     rcx, rbx; pEvent
0x18001c6e0  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18001c6e5  test    eax, eax
0x18001c6e7  jnz     loc_18001C788
0x18001c6ed  lea     rax, [rsp+170h+var_100]
0x18001c6f2  mov     qword ptr [rsp+170h+var_108], rax
0x18001c6f7  xorps   xmm0, xmm0
0x18001c6fa  movdqu  [rsp+170h+var_100], xmm0
0x18001c700  mov     [rbp+70h+var_F0], rsi
0x18001c704  mov     rdx, qword ptr [rsp+170h+var_120+8]
0x18001c709  sub     rdx, r14
0x18001c70c  sar     rdx, 3
0x18001c710  lea     r9, [rsp+170h+var_120+8]
0x18001c715  lea     r8, [rsp+170h+var_120]
0x18001c71a  lea     rcx, [rsp+170h+var_100]
0x18001c71f  call    ??$_Construct_n@AEBQEA_KAEBQEA_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAX_KAEBQEA_K1@Z; std::vector<unsigned __int64>::_Construct_n<unsigned __int64 * const &,unsigned __int64 * const &>(unsigned __int64,unsigned __int64 * const &,unsigned __int64 * const &)
0x18001c724  nop
0x18001c725  xorps   xmm0, xmm0
0x18001c728  movups  [rbp+70h+var_E8], xmm0
0x18001c72c  mov     [rbp+70h+var_D8], rsi
0x18001c730  mov     [rbp+70h+var_D0], rsi
0x18001c734  lea     rdx, [rbp+70h+S1]
  ... truncated ...
```
