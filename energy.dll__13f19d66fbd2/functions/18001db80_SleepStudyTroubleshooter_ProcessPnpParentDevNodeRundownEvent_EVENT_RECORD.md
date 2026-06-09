# SleepStudyTroubleshooter::ProcessPnpParentDevNodeRundownEvent(_EVENT_RECORD *)

- ea: `0x18001db80`
- end: `0x18001e08f`
- name: `?ProcessPnpParentDevNodeRundownEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `1295`
- prototype: `void(SleepStudyTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180006350`
- `0x180008740`
- `0x180009760`
- `0x1800162e0`
- `0x18001be60`
- `0x18001db80`
- `0x18001e790`
- `0x18003bb60`
- `0x18003bf74`
- `0x18003dfdc`
- `0x1800431ac`
- `0x18004ca90`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dff9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dff9`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetPropertySize` at `0x18001dc1d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetPropertySize` at `0x18001dcb2`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetPropertySize` at `0x18001dc1d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetPropertySize` at `0x18001dcb2`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001dc6d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001dcff`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001df25`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001df64`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001dc6d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001dcff`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001df25`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001df64`

## string_xrefs

- `0x18001ddc0`: `InstancePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SleepStudyTroubleshooter::ProcessPnpParentDevNodeRundownEvent(
        SleepStudyTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  TDHSTATUS Property; // eax
  TDHSTATUS v5; // eax
  __int64 v6; // r14
  __int64 *v7; // rsi
  __int64 v8; // rbx
  ULONGLONG v9; // rcx
  __int64 v10; // r8
  ULONGLONG v11; // rdx
  char v12; // r10
  ULONGLONG *v13; // rax
  __int64 inserted; // rax
  ULONGLONG v15; // rsi
  __int64 v16; // rdx
  ULONGLONG v17; // rcx
  __int64 v18; // r9
  ULONGLONG v19; // r8
  char v20; // r11
  ULONGLONG *v21; // rax
  __int64 v22; // rcx
  __int128 *v23; // rdx
  char *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rbx
  _QWORD *v28; // rdi
  ULONG pPropertySize; // [rsp+40h] [rbp-59h] BYREF
  BYTE v30[8]; // [rsp+48h] [rbp-51h] BYREF
  BYTE pBuffer[8]; // [rsp+50h] [rbp-49h] BYREF
  PROPERTY_DATA_DESCRIPTOR v32; // [rsp+58h] [rbp-41h]
  BYTE v33[16]; // [rsp+70h] [rbp-29h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+80h] [rbp-19h] BYREF
  __int128 v35; // [rsp+90h] [rbp-9h] BYREF
  __int64 v36; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v37; // [rsp+A8h] [rbp+Fh]

  v35 = 0;
  v36 = 0;
  v37 = 0;
  std::wstring::_Construct_empty(&v35);
  *(_QWORD *)pBuffer = 0;
  *(_QWORD *)v33 = 0;
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_51;
  pPropertySize = 0;
  *(_QWORD *)v30 = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"DevNode";
  if ( TdhGetPropertySize(a2, 0, 0, 1u, &pPropertyData, &pPropertySize) )
  {
    *(_QWORD *)pBuffer = 0;
    goto LABEL_67;
  }
  if ( pPropertySize == 4 )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"DevNode";
    Property = TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, v30);
    *(_QWORD *)pBuffer = *(_QWORD *)v30;
  }
  else
  {
    if ( pPropertySize != 8 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"DevNode";
    Property = TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer);
  }
  if ( Property )
    goto LABEL_67;
  pPropertySize = 0;
  *(_QWORD *)v30 = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ParentDevNode";
  if ( TdhGetPropertySize(a2, 0, 0, 1u, &pPropertyData, &pPropertySize) )
  {
    *(_QWORD *)v33 = 0;
    goto LABEL_67;
  }
  if ( pPropertySize == 4 )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"ParentDevNode";
    v5 = TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, v30);
    v6 = *(_QWORD *)v30;
    *(_QWORD *)v33 = *(_QWORD *)v30;
  }
  else
  {
    if ( pPropertySize != 8 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"ParentDevNode";
    v5 = TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, v33);
    v6 = *(_QWORD *)v33;
  }
  if ( v5 )
    goto LABEL_67;
  v7 = (__int64 *)(*((_QWORD *)this + 4) + 288LL);
  v8 = *v7;
  v9 = *(_QWORD *)(*v7 + 8);
  v32.Reserved = 0;
  v10 = v8;
  v11 = v9;
  if ( !*(_BYTE *)(v9 + 25) )
  {
    do
    {
      if ( *(_QWORD *)(v11 + 32) >= *(_QWORD *)pBuffer )
      {
        v12 = 0;
        v10 = v11;
      }
      else
      {
        v12 = 1;
      }
      v13 = (ULONGLONG *)(v11 + 16);
      if ( !v12 )
        v13 = (ULONGLONG *)v11;
      v11 = *v13;
    }
    while ( !*(_BYTE *)(*v13 + 25) );
  }
  if ( v10 == v8 || *(_BYTE *)(v10 + 25) || *(_QWORD *)pBuffer < *(_QWORD *)(v10 + 32) )
  {
    v32 = (PROPERTY_DATA_DESCRIPTOR)v9;
    inserted = v8;
    while ( !*(_BYTE *)(v9 + 25) )
    {
      v32.PropertyName = v9;
      if ( *(_QWORD *)(v9 + 32) < *(_QWORD *)pBuffer )
      {
        v32.ArrayIndex = 0;
        v9 += 16LL;
      }
      else
      {
        v32.ArrayIndex = 1;
        inserted = v9;
      }
      v9 = *(_QWORD *)v9;
    }
    if ( *(_BYTE *)(inserted + 25) || *(_QWORD *)pBuffer < *(_QWORD *)(inserted + 32) )
    {
      if ( v7[1] == 0x555555555555555LL )
        std::_Xlength_error("map/set too long");
      pPropertyData.PropertyName = (ULONGLONG)v7;
      *(_QWORD *)&pPropertyData.ArrayIndex = 0;
      v24 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
      *(_QWORD *)v30 = pBuffer;
      ____0AEB_K__Z__V___pair___CB_K_K_std__QEAA_Upiecewise_construct_t_1_V__tuple_AEB_K_1_V__tuple___V_1__Z(
        v24 + 32,
        v25,
        v30);
      *(_QWORD *)v26 = v8;
      *(_QWORD *)(v26 + 8) = v8;
      *(_QWORD *)(v26 + 16) = v8;
      *(_WORD *)(v26 + 24) = 0;
      pPropertyData = v32;
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Domain>>>::_Insert_node(
                   v7,
                   &pPropertyData,
                   v26);
    }
    *(_QWORD *)(inserted + 40) = v6;
  }
  if ( a2->EventHeader.EventDescriptor.Version )
  {
    if ( !(unsigned int)GetEventProperty(a2) )
    {
      v15 = *((_QWORD *)this + 4) + 304LL;
      v16 = *(_QWORD *)v15;
      v17 = *(_QWORD *)(*(_QWORD *)v15 + 8LL);
      v32.Reserved = 0;
      v18 = v16;
      v19 = v17;
      if ( !*(_BYTE *)(v17 + 25) )
      {
        do
        {
          if ( *(_QWORD *)(v19 + 32) < *(_QWORD *)pBuffer )
          {
            v20 = 1;
          }
          else
          {
            v20 = 0;
            v18 = v19;
          }
          v21 = (ULONGLONG *)(v19 + 16);
          if ( !v20 )
            v21 = (ULONGLONG *)v19;
          v19 = *v21;
        }
        while ( !*(_BYTE *)(*v21 + 25) );
      }
      if ( v18 == v16 || *(_BYTE *)(v18 + 25) || *(_QWORD *)pBuffer < *(_QWORD *)(v18 + 32) )
      {
        v32 = (PROPERTY_DATA_DESCRIPTOR)v17;
        while ( !*(_BYTE *)(v17 + 25) )
        {
          v32.PropertyName = v17;
          if ( *(_QWORD *)(v17 + 32) < *(_QWORD *)pBuffer )
          {
            v32.ArrayIndex = 0;
            v17 += 16LL;
          }
          else
          {
            v32.ArrayIndex = 1;
            v16 = v17;
          }
          v17 = *(_QWORD *)v17;
        }
        if ( *(_BYTE *)(v16 + 25) || *(_QWORD *)pBuffer < *(_QWORD *)(v16 + 32) )
        {
          std::_Tree<std::_Tmap_traits<unsigned __int64,std::wstring,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::wstring>>,0>>::_Check_grow_by_1(
            v15,
            v16,
            v19);
          pPropertyData.PropertyName = v15;
          *(_QWORD *)&pPropertyData.ArrayIndex = 0;
          v27 = *(_QWORD *)v15;
          v28 = std::_Allocate<16,std::_Default_allocate_traits>(0x48u);
          *(_QWORD *)v30 = pBuffer;
          ____0V__tuple_AEB_K_std__V__tuple___V_1__0A___Z_S___pair___CB_KV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std__AEAA_AEAV__tuple_AEB_K_1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
            v28 + 4,
            v30);
          *v28 = v27;
          v28[1] = v27;
          v28[2] = v27;
          *((_WORD *)v28 + 12) = 0;
          pPropertyData = v32;
          v16 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Domain>>>::_Insert_node(
                  v15,
                  &pPropertyData,
                  v28);
        }
        v22 = v16 + 40;
        if ( (__int128 *)(v16 + 40) != &v35 )
        {
          v23 = &v35;
          if ( v37 > 7 )
            v23 = (__int128 *)v35;
          std::wstring::assign(v22, v23, v36);
        }
      }
      goto LABEL_51;
    }
LABEL_67:
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_51:
  if ( v37 > 7 )
    std::_Deallocate<16>((void *)v35, 2 * v37 + 2);
}

```

## disassembly

```asm
0x18001db80  mov     [rsp-8+arg_10], rbx
0x18001db85  push    rbp
0x18001db86  push    rsi
0x18001db87  push    rdi
0x18001db88  push    r12
0x18001db8a  push    r13
0x18001db8c  push    r14
0x18001db8e  push    r15
0x18001db90  lea     rbp, [rsp-27h]
0x18001db95  sub     rsp, 0C0h
0x18001db9c  mov     rax, cs:__security_cookie
0x18001dba3  xor     rax, rsp
0x18001dba6  mov     [rbp+57h+var_40], rax
0x18001dbaa  mov     rdi, rdx
0x18001dbad  mov     r15, rcx
0x18001dbb0  xorps   xmm0, xmm0
0x18001dbb3  movups  [rbp+57h+var_60], xmm0
0x18001dbb7  xor     r12d, r12d
0x18001dbba  mov     [rbp+57h+var_50], r12
0x18001dbbe  mov     [rbp+57h+var_48], r12
0x18001dbc2  lea     rcx, [rbp+57h+var_60]
0x18001dbc6  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001dbcb  nop
0x18001dbcc  mov     qword ptr [rbp+57h+var_A0], r12
0x18001dbd0  mov     qword ptr [rbp+57h+var_80], r12
0x18001dbd4  cmp     [r15+20h], r12
0x18001dbd8  jz      loc_18001DE8B
0x18001dbde  mov     [rbp+57h+var_B0], r12d
0x18001dbe2  mov     qword ptr [rbp+57h+var_A8], r12
0x18001dbe6  mov     [rbp+57h+var_70.Reserved], r12d
0x18001dbea  or      esi, 0FFFFFFFFh
0x18001dbed  mov     [rbp+57h+var_70.ArrayIndex], esi
0x18001dbf0  lea     r14, aDevnode; "DevNode"
0x18001dbf7  mov     [rbp+57h+var_70.PropertyName], r14
0x18001dbfb  lea     rax, [rbp+57h+var_B0]
0x18001dbff  mov     [rsp+0F0h+pPropertySize], rax; pPropertySize
0x18001dc04  lea     rax, [rbp+57h+var_70]
0x18001dc08  mov     [rsp+0F0h+pPropertyData], rax; pPropertyData
0x18001dc0d  lea     r13d, [r12+1]
0x18001dc12  mov     r9d, r13d; PropertyDataCount
0x18001dc15  xor     r8d, r8d; pTdhContext
0x18001dc18  xor     edx, edx; TdhContextCount
0x18001dc1a  mov     rcx, rdi; pEvent
0x18001dc1d  call    cs:__imp_TdhGetPropertySize
0x18001dc23  test    eax, eax
0x18001dc25  jnz     loc_18001E000
0x18001dc2b  lea     ebx, [rax+8]
0x18001dc2e  cmp     [rbp+57h+var_B0], 4
0x18001dc32  jz      loc_18001DEF9
0x18001dc38  cmp     [rbp+57h+var_B0], ebx
0x18001dc3b  jnz     loc_18001DF77
0x18001dc41  mov     [rbp+57h+var_70.Reserved], r12d
0x18001dc45  mov     [rbp+57h+var_70.ArrayIndex], esi
0x18001dc48  mov     [rbp+57h+var_70.PropertyName], r14
0x18001dc4c  lea     rax, [rbp+57h+var_A0]
0x18001dc50  mov     [rsp+0F0h+pBuffer], rax; pBuffer
0x18001dc55  mov     dword ptr [rsp+0F0h+pPropertySize], ebx; BufferSize
0x18001dc59  lea     rax, [rbp+57h+var_70]
0x18001dc5d  mov     [rsp+0F0h+pPropertyData], rax; pPropertyData
0x18001dc62  mov     r9d, r13d; PropertyDataCount
0x18001dc65  xor     r8d, r8d; pTdhContext
0x18001dc68  xor     edx, edx; TdhContextCount
0x18001dc6a  mov     rcx, rdi; pEvent
0x18001dc6d  call    cs:__imp_TdhGetProperty
0x18001dc73  test    eax, eax
0x18001dc75  jnz     loc_18001E004
0x18001dc7b  mov     [rbp+57h+var_B0], r12d
0x18001dc7f  mov     qword ptr [rbp+57h+var_A8], r12
0x18001dc83  mov     [rbp+57h+var_70.Reserved], r12d
0x18001dc87  mov     [rbp+57h+var_70.ArrayIndex], esi
0x18001dc8a  lea     r14, aParentdevnode; "ParentDevNode"
0x18001dc91  mov     [rbp+57h+var_70.PropertyName], r14
0x18001dc95  lea     rax, [rbp+57h+var_B0]
0x18001dc99  mov     [rsp+0F0h+pPropertySize], rax; pPropertySize
0x18001dc9e  lea     rax, [rbp+57h+var_70]
0x18001dca2  mov     [rsp+0F0h+pPropertyData], rax; pPropertyData
0x18001dca7  mov     r9d, r13d; PropertyDataCount
0x18001dcaa  xor     r8d, r8d; pTdhContext
0x18001dcad  xor     edx, edx; TdhContextCount
0x18001dcaf  mov     rcx, rdi; pEvent
0x18001dcb2  call    cs:__imp_TdhGetPropertySize
0x18001dcb8  test    eax, eax
0x18001dcba  jnz     loc_18001E00E
0x18001dcc0  cmp     [rbp+57h+var_B0], 4
0x18001dcc4  jz      loc_18001DF38
0x18001dcca  cmp     [rbp+57h+var_B0], ebx
0x18001dccd  jnz     loc_18001DF81
0x18001dcd3  mov     [rbp+57h+var_70.Reserved], r12d
0x18001dcd7  mov     [rbp+57h+var_70.ArrayIndex], esi
0x18001dcda  mov     [rbp+57h+var_70.PropertyName], r14
0x18001dcde  lea     rax, [rbp+57h+var_80]
0x18001dce2  mov     [rsp+0F0h+pBuffer], rax; pBuffer
0x18001dce7  mov     dword ptr [rsp+0F0h+pPropertySize], ebx; BufferSize
0x18001dceb  lea     rax, [rbp+57h+var_70]
0x18001dcef  mov     [rsp+0F0h+pPropertyData], rax; pPropertyData
0x18001dcf4  mov     r9d, r13d; PropertyDataCount
0x18001dcf7  xor     r8d, r8d; pTdhContext
0x18001dcfa  xor     edx, edx; TdhContextCount
0x18001dcfc  mov     rcx, rdi; pEvent
0x18001dcff  call    cs:__imp_TdhGetProperty
0x18001dd05  mov     r14, qword ptr [rbp+57h+var_80]
0x18001dd09  test    eax, eax
0x18001dd0b  jnz     loc_18001E004
0x18001dd11  mov     rsi, [r15+20h]
0x18001dd15  add     rsi, 120h
0x18001dd1c  mov     rbx, [rsi]
0x18001dd1f  mov     rcx, [rbx+8]
0x18001dd23  xor     eax, eax
0x18001dd25  mov     [rbp+57h+var_98.Reserved], eax
0x18001dd28  mov     r8, rbx
0x18001dd2b  mov     rdx, rcx
0x18001dd2e  mov     r9, qword ptr [rbp+57h+var_A0]
0x18001dd32  cmp     [rcx+19h], r12b
0x18001dd36  jnz     short loc_18001DD55
0x18001dd38  cmp     [rdx+20h], r9
0x18001dd3c  jnb     short loc_18001DD6B
0x18001dd3e  mov     r10b, r13b
0x18001dd41  lea     rax, [rdx+10h]
0x18001dd45  test    r10b, r10b
0x18001dd48  cmovz   rax, rdx
0x18001dd4c  mov     rdx, [rax]
0x18001dd4f  cmp     [rdx+19h], r12b
0x18001dd53  jz      short loc_18001DD38
0x18001dd55  cmp     r8, rbx
0x18001dd58  jnz     loc_18001DE39
0x18001dd5e  mov     [rbp+57h+var_98.PropertyName], rcx
0x18001dd62  mov     qword ptr [rbp+57h+var_98.ArrayIndex], r12
0x18001dd66  mov     rax, rbx
0x18001dd69  jmp     short loc_18001DD7E
0x18001dd6b  mov     r10b, r12b
0x18001dd6e  mov     r8, rdx
0x18001dd71  jmp     short loc_18001DD41
0x18001dd73  mov     [rbp+57h+var_98.ArrayIndex], r12d
0x18001dd77  add     rcx, 10h
0x18001dd7b  mov     rcx, [rcx]
0x18001dd7e  cmp     [rcx+19h], r12b
0x18001dd82  jnz     short loc_18001DD97
0x18001dd84  mov     [rbp+57h+var_98.PropertyName], rcx
0x18001dd88  cmp     [rcx+20h], r9
0x18001dd8c  jb      short loc_18001DD73
0x18001dd8e  mov     [rbp+57h+var_98.ArrayIndex], r13d
0x18001dd92  mov     rax, rcx
0x18001dd95  jmp     short loc_18001DD7B
0x18001dd97  cmp     [rax+19h], r12b
0x18001dd9b  jnz     loc_18001DF8B
0x18001dda1  cmp     r9, [rax+20h]
0x18001dda5  jb      loc_18001DF8B
0x18001ddab  mov     [rax+28h], r14
0x18001ddaf  cmp     [rdi+2Ah], r13b
0x18001ddb3  jb      loc_18001DE8B
0x18001ddb9  xor     r9d, r9d
0x18001ddbc  lea     r8, [rbp+57h+var_60]
0x18001ddc0  lea     rdx, aInstancepath; "InstancePath"
0x18001ddc7  mov     rcx, rdi; pEvent
0x18001ddca  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18001ddcf  test    eax, eax
0x18001ddd1  jnz     loc_18001E004
0x18001ddd7  mov     rsi, [r15+20h]
0x18001dddb  add     rsi, 130h
0x18001dde2  mov     rdx, [rsi]
0x18001dde5  mov     rcx, [rdx+8]
0x18001dde9  xor     eax, eax
0x18001ddeb  mov     [rbp+57h+var_98.Reserved], eax
0x18001ddee  mov     r9, rdx
0x18001ddf1  mov     r8, rcx
0x18001ddf4  mov     r10, qword ptr [rbp+57h+var_A0]
0x18001ddf8  cmp     [rcx+19h], r12b
0x18001ddfc  jnz     short loc_18001DE1E
0x18001ddfe  cmp     [r8+20h], r10
0x18001de02  jb      short loc_18001DE34
0x18001de04  mov     r11b, r12b
0x18001de07  mov     r9, r8
0x18001de0a  lea     rax, [r8+10h]
0x18001de0e  test    r11b, r11b
0x18001de11  cmovz   rax, r8
0x18001de15  mov     r8, [rax]
0x18001de18  cmp     [r8+19h], r12b
0x18001de1c  jz      short loc_18001DDFE
0x18001de1e  cmp     r9, rdx
0x18001de21  jnz     loc_18001DEE4
0x18001de27  mov     [rbp+57h+var_98.PropertyName], rcx
0x18001de2b  mov     qword ptr [rbp+57h+var_98.ArrayIndex], r12
0x18001de2f  jmp     loc_18001DECB
0x18001de34  mov     r11b, r13b
0x18001de37  jmp     short loc_18001DE0A
0x18001de39  cmp     [r8+19h], r12b
0x18001de3d  jnz     loc_18001DD5E
0x18001de43  cmp     r9, [r8+20h]
0x18001de47  jnb     loc_18001DDAF
0x18001de4d  jmp     loc_18001DD5E
0x18001de52  cmp     [rdx+19h], r12b
0x18001de56  jnz     loc_18001E014
0x18001de5c  cmp     r10, [rdx+20h]
0x18001de60  jb      loc_18001E014
0x18001de66  lea     rcx, [rdx+28h]
0x18001de6a  lea     rax, [rbp+57h+var_60]
0x18001de6e  cmp     rcx, rax
0x18001de71  jz      short loc_18001DE8B
0x18001de73  lea     rdx, [rbp+57h+var_60]
0x18001de77  cmp     [rbp+57h+var_48], 7
0x18001de7c  cmova   rdx, qword ptr [rbp+57h+var_60]
0x18001de81  mov     r8, [rbp+57h+var_50]
0x18001de85  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18001de8a  nop
0x18001de8b  mov     rdx, [rbp+57h+var_48]
0x18001de8f  cmp     rdx, 7
0x18001de93  ja      loc_18001E079
0x18001de99  mov     rcx, [rbp+57h+var_40]
0x18001de9d  xor     rcx, rsp; StackCookie
0x18001dea0  call    __security_check_cookie
0x18001dea5  mov     rbx, [rsp+0F0h+arg_10]
0x18001dead  add     rsp, 0C0h
0x18001deb4  pop     r15
0x18001deb6  pop     r14
0x18001deb8  pop     r13
0x18001deba  pop     r12
0x18001debc  pop     rdi
0x18001debd  pop     rsi
0x18001debe  pop     rbp
0x18001debf  retn
0x18001dec0  mov     [rbp+57h+var_98.ArrayIndex], r12d
0x18001dec4  add     rcx, 10h
0x18001dec8  mov     rcx, [rcx]
0x18001decb  cmp     [rcx+19h], r12b
0x18001decf  jnz     short loc_18001DE52
0x18001ded1  mov     [rbp+57h+var_98.PropertyName], rcx
0x18001ded5  cmp     [rcx+20h], r10
0x18001ded9  jb      short loc_18001DEC0
0x18001dedb  mov     [rbp+57h+var_98.ArrayIndex], r13d
0x18001dedf  mov     rdx, rcx
0x18001dee2  jmp     short loc_18001DEC8
0x18001dee4  cmp     [r9+19h], r12b
0x18001dee8  jnz     loc_18001DE27
0x18001deee  cmp     r10, [r9+20h]
0x18001def2  jnb     short loc_18001DE8B
0x18001def4  jmp     loc_18001DE27
0x18001def9  mov     [rbp+57h+var_70.Reserved], r12d
0x18001defd  mov     [rbp+57h+var_70.ArrayIndex], esi
0x18001df00  mov     [rbp+57h+var_70.PropertyName], r14
0x18001df04  lea     rax, [rbp+57h+var_A8]
0x18001df08  mov     [rsp+0F0h+pBuffer], rax; pBuffer
0x18001df0d  mov     dword ptr [rsp+0F0h+pPropertySize], ebx; BufferSize
0x18001df11  lea     rax, [rbp+57h+var_70]
0x18001df15  mov     [rsp+0F0h+pPropertyData], rax; pPropertyData
0x18001df1a  mov     r9d, r13d; PropertyDataCount
0x18001df1d  xor     r8d, r8d; pTdhContext
0x18001df20  xor     edx, edx; TdhContextCount
0x18001df22  mov     rcx, rdi; pEvent
0x18001df25  call    cs:__imp_TdhGetProperty
0x18001df2b  mov     rcx, qword ptr [rbp+57h+var_A8]
0x18001df2f  mov     qword ptr [rbp+57h+var_A0], rcx
0x18001df33  jmp     loc_18001DC73
0x18001df38  mov     [rbp+57h+var_70.Reserved], r12d
0x18001df3c  mov     [rbp+57h+var_70.ArrayIndex], esi
0x18001df3f  mov     [rbp+57h+var_70.PropertyName], r14
0x18001df43  lea     rax, [rbp+57h+var_A8]
0x18001df47  mov     [rsp+0F0h+pBuffer], rax; pBuffer
0x18001df4c  mov     dword ptr [rsp+0F0h+pPropertySize], ebx; BufferSize
0x18001df50  lea     rax, [rbp+57h+var_70]
0x18001df54  mov     [rsp+0F0h+pPropertyData], rax; pPropertyData
0x18001df59  mov     r9d, r13d; PropertyDataCount
0x18001df5c  xor     r8d, r8d; pTdhContext
0x18001df5f  xor     edx, edx; TdhContextCount
0x18001df61  mov     rcx, rdi; pEvent
0x18001df64  call    cs:__imp_TdhGetProperty
0x18001df6a  mov     r14, qword ptr [rbp+57h+var_A8]
0x18001df6e  mov     qword ptr [rbp+57h+var_80], r14
0x18001df72  jmp     loc_18001DD09
0x18001df77  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001df7c  jmp     loc_18001DC41
0x18001df81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001df86  jmp     loc_18001DCD3
0x18001df8b  mov     rax, 555555555555555h
0x18001df95  cmp     [rsi+8], rax
0x18001df99  jz      short loc_18001DFF2
0x18001df9b  mov     [rbp+57h+var_70.PropertyName], rsi
0x18001df9f  mov     qword ptr [rbp+57h+var_70.ArrayIndex], r12
0x18001dfa3  mov     ecx, 30h ; '0'
0x18001dfa8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001dfad  mov     r9, rax
0x18001dfb0  lea     rax, [rbp+57h+var_A0]
0x18001dfb4  mov     qword ptr [rbp+57h+var_A8], rax
0x18001dfb8  lea     rcx, [r9+20h]
0x18001dfbc  lea     r8, [rbp+57h+var_A8]
0x18001dfc0  call    ??$?0AEB_K$$Z$$V@?$pair@$$CB_K_K@std@@QEAA@Upiecewise_construct_t@1@V?$tuple@AEB_K@1@V?$tuple@$$V@1@@Z
0x18001dfc5  mov     [r9], rbx
0x18001dfc8  mov     [r9+8], rbx
0x18001dfcc  mov     [r9+10h], rbx
0x18001dfd0  mov     [r9+18h], r12w
0x18001dfd5  movups  xmm0, xmmword ptr [rbp+57h+var_98.PropertyName]
0x18001dfd9  movdqu  xmmword ptr [rbp+57h+var_70.PropertyName], xmm0
0x18001dfde  mov     r8, r9
0x18001dfe1  lea     rdx, [rbp+57h+var_70]
0x18001dfe5  mov     rcx, rsi
0x18001dfe8  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVDomain@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKVDomain@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKVDomain@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Domain>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,Domain>,void *> *>,std::_Tree_node<std::pair<ulong const,Domain>,void *> * const)
0x18001dfed  jmp     loc_18001DDAB
0x18001dff2  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001dff9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001e000  mov     qword ptr [rbp+57h+var_A0], r12
0x18001e004  call    MicrosoftTelemetryAssertTriggeredNoArgs
  ... truncated ...
```
