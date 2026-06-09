# TaskbarTip::_tip_PrimaryTaskbarInitialization::evaluate(void)

- ea: `0x140064d10`
- end: `0x1400655e4`
- name: `?evaluate@_tip_PrimaryTaskbarInitialization@TaskbarTip@@QEAAXXZ`
- size: `2260`
- prototype: `void __fastcall(TaskbarTip::_tip_PrimaryTaskbarInitialization *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x140127150`

## callees

- `0x140064d10`
- `0x1400655ec`

## string_xrefs

- `0x14006533b`: `reason::control_not_created_tasklist`
- `0x140064fea`: `reason::taskbar_not_created`
- `0x1400651c8`: `reason::control_not_created_back`
- `0x14006513e`: `reason::failed_to_init_taskbar_position`
- `0x140065280`: `reason::control_not_created_searchcontrol`
- `0x14006559a`: `reason::taskband_accessible_title_not_set`
- `0x1400652dc`: `reason::control_not_created_rebar`
- `0x140065110`: `reason::failed_to_determine_or_load_taskbar_placement`
- `0x14006516c`: `reason::failed_to_determine_primary_taskbar_location`
- `0x1400652ae`: `reason::control_not_created_deskbandsite`
- `0x140064d4f`: `reason::failed_to_start_syncthread`
- `0x140065408`: `reason::control_uninitialized_taskview`
- `0x14006530a`: `reason::control_not_created_taskband`
- `0x140064e44`: `reason::control_failed_initialization_taskview`
- `0x140065224`: `reason::control_not_created_taskview`
- `0x140065516`: `reason::control_uninitialized_taskband`
- `0x140065252`: `reason::control_not_created_cortana`
- `0x1400651f6`: `reason::control_not_created_searchbutton`
- `0x14006519a`: `reason::control_not_created_pearl`
- `0x140065542`: `reason::control_uninitialized_tasklist`
- `0x140064f8b`: `reason::control_failed_initialization_tasklist`
- `0x140064fbc`: `reason::failed_to_identify_taskbar_rule`
- `0x140064f58`: `reason::control_failed_initialization_taskband`

## pseudocode

```c
void __fastcall TaskbarTip::_tip_PrimaryTaskbarInitialization::evaluate(
        TaskbarTip::_tip_PrimaryTaskbarInitialization *this,
        const char *a2)
{
  __int64 v2; // r8
  const char *v3; // rax
  __int64 v4; // r8
  char v5; // r9
  char v6; // r9
  char v7; // r9
  char v8; // r9
  char v9; // r9
  char v10; // r9
  char v11; // r9
  char v12; // r9
  char v13; // r9
  char v14; // r9
  char v15; // r9
  char v16; // r9
  int v17; // eax
  char v18; // r9
  char v19; // r9
  __int16 v20; // r11
  char v21; // r9
  const char *v22; // r10
  char v23; // r9
  char v24; // r9
  char v25; // r9
  char v26; // r9
  char v27; // r9
  char v28; // r9
  char v29; // r9
  char v30; // r9
  char v31; // r9
  char v32; // r9
  char v33; // r9
  char v34; // r9
  char v35; // r9
  char v36; // r9
  char v37; // r9
  char v38; // r9
  char v39; // r9
  const char *v40; // rax
  char v41; // cl
  char v42; // r9
  char v43; // r9
  char v44; // r9
  char v45; // r9
  char v46; // r9
  char v47; // r9
  char v48; // r9
  char v49; // r9
  char v50; // r9
  char v51; // r9
  char v52; // r9
  char v53; // r9
  char v54; // r9

  v2 = *((_QWORD *)this + 1);
  if ( (*(_DWORD *)(v2 + 56) & 0x200) == 0 )
  {
    if ( *(_BYTE *)(v2 + 152) )
      return;
    *(_BYTE *)(v2 + 152) = 3;
    *(_WORD *)(v2 + 154) = 16385;
LABEL_150:
    *(_QWORD *)(v2 + 160) = 0;
    return;
  }
  if ( !*((_BYTE *)this + 16) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_start_syncthread", a2);
    if ( *(_BYTE *)(v4 + 152) != v5 )
      return;
    *(_WORD *)(v4 + 154) = 1;
    goto LABEL_7;
  }
  if ( *((_BYTE *)this + 29) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failure_from_gdi_handle_overflow", a2);
    if ( *(_BYTE *)(v4 + 152) != v6 )
      return;
    *(_WORD *)(v4 + 154) = 89;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 8) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_pearl", a2);
    if ( *(_BYTE *)(v4 + 152) != v7 )
      return;
    *(_WORD *)(v4 + 154) = 14;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 9) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_back", a2);
    if ( *(_BYTE *)(v4 + 152) != v8 )
      return;
    *(_WORD *)(v4 + 154) = 15;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 10) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_searchbutton", a2);
    if ( *(_BYTE *)(v4 + 152) != v9 )
      return;
    *(_WORD *)(v4 + 154) = 16;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 11) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_taskview", a2);
    if ( *(_BYTE *)(v4 + 152) != v10 )
      return;
    *(_WORD *)(v4 + 154) = 17;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 12) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_cortana", a2);
    if ( *(_BYTE *)(v4 + 152) != v11 )
      return;
    *(_WORD *)(v4 + 154) = 18;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 13) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_searchcontrol", a2);
    if ( *(_BYTE *)(v4 + 152) != v12 )
      return;
    *(_WORD *)(v4 + 154) = 19;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 14) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_deskbandsite", a2);
    if ( *(_BYTE *)(v4 + 152) != v13 )
      return;
    *(_WORD *)(v4 + 154) = 20;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 15) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_rebar", a2);
    if ( *(_BYTE *)(v4 + 152) != v14 )
      return;
    *(_WORD *)(v4 + 154) = 21;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 21) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_pager", a2);
    if ( *(_BYTE *)(v4 + 152) != v15 )
      return;
    *(_WORD *)(v4 + 154) = 27;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 31) == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_taskband", a2);
    if ( *(_BYTE *)(v4 + 152) != v16 )
      return;
    *(_WORD *)(v4 + 154) = 37;
    goto LABEL_7;
  }
  v17 = *((_DWORD *)this + 32);
  if ( v17 == 2 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_failed_initialization_tasklist", a2);
    if ( *(_BYTE *)(v4 + 152) != v18 )
      return;
    *(_WORD *)(v4 + 154) = 38;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 33) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_identify_taskbar_rule", a2);
    if ( *(_BYTE *)(v4 + 152) != v19 )
      return;
    *(_WORD *)(v4 + 154) = 90;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 17) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::taskbar_not_created", a2);
    if ( *(_BYTE *)(v4 + 152) != v21 )
      return;
    *(_WORD *)(v4 + 154) = v20;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 21) )
  {
    v22 = tip2::details::reason_string((tip2::details *)"reason::theme_not_loaded", a2);
    if ( *(_BYTE *)(v2 + 152) != v23 )
      return;
    *(_BYTE *)(v2 + 152) = 3;
    *(_WORD *)(v2 + 154) = 3;
    goto LABEL_53;
  }
  if ( !*((_BYTE *)this + 18) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_init_animations", a2);
    if ( *(_BYTE *)(v4 + 152) != v24 )
      return;
    *(_WORD *)(v4 + 154) = 4;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 19) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_init_window", a2);
    if ( *(_BYTE *)(v4 + 152) != v25 )
      return;
    *(_WORD *)(v4 + 154) = 5;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 20) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::policies_not_loaded", a2);
    if ( *(_BYTE *)(v4 + 152) != v26 )
      return;
    *(_WORD *)(v4 + 154) = 6;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 23) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::cortana_settings_not_loaded", a2);
    if ( *(_BYTE *)(v4 + 152) != v27 )
      return;
    *(_WORD *)(v4 + 154) = 7;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 24) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_determine_or_load_taskbar_placement", a2);
    if ( *(_BYTE *)(v4 + 152) != v28 )
      return;
    *(_WORD *)(v4 + 154) = 8;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 25) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_init_taskbar_position", a2);
    if ( *(_BYTE *)(v4 + 152) != v29 )
      return;
    *(_WORD *)(v4 + 154) = 9;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 26) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_determine_primary_taskbar_location", a2);
    if ( *(_BYTE *)(v4 + 152) != v30 )
      return;
    *(_WORD *)(v4 + 154) = 10;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 8) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_pearl", a2);
    if ( *(_BYTE *)(v4 + 152) != v31 )
      return;
    *(_WORD *)(v4 + 154) = 64;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 9) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_back", a2);
    if ( *(_BYTE *)(v4 + 152) != v32 )
      return;
    *(_WORD *)(v4 + 154) = 65;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 10) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_searchbutton", a2);
    if ( *(_BYTE *)(v4 + 152) != v33 )
      return;
    *(_WORD *)(v4 + 154) = 66;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 11) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_taskview", a2);
    if ( *(_BYTE *)(v4 + 152) != v34 )
      return;
    *(_WORD *)(v4 + 154) = 67;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 12) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_cortana", a2);
    if ( *(_BYTE *)(v4 + 152) != v35 )
      return;
    *(_WORD *)(v4 + 154) = 68;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 13) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_searchcontrol", a2);
    if ( *(_BYTE *)(v4 + 152) != v36 )
      return;
    *(_WORD *)(v4 + 154) = 69;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 14) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_deskbandsite", a2);
    if ( *(_BYTE *)(v4 + 152) != v37 )
      return;
    *(_WORD *)(v4 + 154) = 70;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 15) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_rebar", a2);
    if ( *(_BYTE *)(v4 + 152) != v38 )
      return;
    *(_WORD *)(v4 + 154) = 71;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 31) )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::control_not_created_taskband", a2);
    if ( *(_BYTE *)(v4 + 152) != v39 )
      return;
    *(_WORD *)(v4 + 154) = 87;
    goto LABEL_7;
  }
  if ( v17 )
  {
    if ( *((_DWORD *)this + 8) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_pearl", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v42 )
        return;
      *(_WORD *)(v4 + 154) = 39;
    }
    else if ( *((_DWORD *)this + 9) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_back", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v43 )
        return;
      *(_WORD *)(v4 + 154) = 40;
    }
    else if ( *((_DWORD *)this + 10) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_searchbutton", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v44 )
        return;
      *(_WORD *)(v4 + 154) = 41;
    }
    else if ( *((_DWORD *)this + 11) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_taskview", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v45 )
        return;
      *(_WORD *)(v4 + 154) = 42;
    }
    else if ( *((_DWORD *)this + 12) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_cortana", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v46 )
        return;
      *(_WORD *)(v4 + 154) = 43;
    }
    else if ( *((_DWORD *)this + 13) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_searchcontrol", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v47 )
        return;
      *(_WORD *)(v4 + 154) = 44;
    }
    else if ( *((_DWORD *)this + 14) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_deskbandsite", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v48 )
        return;
      *(_WORD *)(v4 + 154) = 45;
    }
    else if ( *((_DWORD *)this + 15) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_rebar", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v49 )
        return;
      *(_WORD *)(v4 + 154) = 46;
    }
    else if ( *((_DWORD *)this + 21) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_pager", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v50 )
        return;
      *(_WORD *)(v4 + 154) = 52;
    }
    else if ( *((_DWORD *)this + 31) == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_taskband", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v51 )
        return;
      *(_WORD *)(v4 + 154) = 62;
    }
    else if ( v17 == 1 )
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::control_uninitialized_tasklist", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v52 )
        return;
      *(_WORD *)(v4 + 154) = 63;
    }
    else if ( *((_BYTE *)this + 27) )
    {
      if ( *((_BYTE *)this + 28) )
      {
        if ( *(_BYTE *)(v2 + 152) )
          return;
        *(_BYTE *)(v2 + 152) = 1;
        *(_WORD *)(v2 + 154) = 0x8000;
        goto LABEL_150;
      }
      v3 = tip2::details::reason_string((tip2::details *)"reason::taskband_accessible_title_not_set", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v54 )
        return;
      *(_WORD *)(v4 + 154) = 13;
    }
    else
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::failed_to_init_immersiveshell", (const char *)1);
      if ( *(_BYTE *)(v4 + 152) != v53 )
        return;
      *(_WORD *)(v4 + 154) = 12;
    }
LABEL_7:
    *(_BYTE *)(v4 + 152) = 3;
    *(_QWORD *)(v4 + 160) = v3;
    return;
  }
  v40 = "reason::control_not_created_tasklist";
  v41 = 114;
  v22 = "reason::control_not_created_tasklist";
  do
  {
    ++v40;
    if ( v41 == 58 )
      v22 = v40;
    v41 = *v40;
  }
  while ( *v40 );
  if ( !*(_BYTE *)(v2 + 152) )
  {
    *(_BYTE *)(v2 + 152) = 3;
    *(_WORD *)(v2 + 154) = 88;
LABEL_53:
    *(_QWORD *)(v2 + 160) = v22;
  }
}

```

## disassembly

```asm
0x140064d10  sub     rsp, 28h
0x140064d14  mov     r8, [rcx+8]
0x140064d18  xor     r9d, r9d
0x140064d1b  test    dword ptr [r8+38h], 200h
0x140064d23  jnz     short loc_140064D49
0x140064d25  cmp     [r8+98h], r9b
0x140064d2c  jnz     loc_1400655DF
0x140064d32  mov     byte ptr [r8+98h], 3
0x140064d3a  mov     word ptr [r8+9Ah], 4001h
0x140064d44  jmp     loc_1400655D8
0x140064d49  cmp     [rcx+10h], r9b
0x140064d4d  jnz     short loc_140064D86
0x140064d4f  lea     rcx, aReasonFailedTo_2; "reason::failed_to_start_syncthread"
0x140064d56  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064d5b  cmp     [r8+98h], r9b
0x140064d62  jnz     loc_1400655DF
0x140064d68  mov     word ptr [r8+9Ah], 1
0x140064d72  mov     byte ptr [r8+98h], 3
0x140064d7a  mov     [r8+0A0h], rax
0x140064d81  jmp     loc_1400655DF
0x140064d86  cmp     [rcx+1Dh], r9b
0x140064d8a  jz      short loc_140064DB1
0x140064d8c  lea     rcx, aReasonFailureF; "reason::failure_from_gdi_handle_overflo"...
0x140064d93  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064d98  cmp     [r8+98h], r9b
0x140064d9f  jnz     loc_1400655DF
0x140064da5  mov     word ptr [r8+9Ah], 59h ; 'Y'
0x140064daf  jmp     short loc_140064D72
0x140064db1  mov     r11d, 2
0x140064db7  cmp     [rcx+20h], r11d
0x140064dbb  jnz     short loc_140064DE2
0x140064dbd  lea     rcx, aReasonControlF; "reason::control_failed_initialization_p"...
0x140064dc4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064dc9  cmp     [r8+98h], r9b
0x140064dd0  jnz     loc_1400655DF
0x140064dd6  mov     word ptr [r8+9Ah], 0Eh
0x140064de0  jmp     short loc_140064D72
0x140064de2  cmp     [rcx+24h], r11d
0x140064de6  jnz     short loc_140064E10
0x140064de8  lea     rcx, aReasonControlF_6; "reason::control_failed_initialization_b"...
0x140064def  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064df4  cmp     [r8+98h], r9b
0x140064dfb  jnz     loc_1400655DF
0x140064e01  mov     word ptr [r8+9Ah], 0Fh
0x140064e0b  jmp     loc_140064D72
0x140064e10  cmp     [rcx+28h], r11d
0x140064e14  jnz     short loc_140064E3E
0x140064e16  lea     rcx, aReasonControlF_3; "reason::control_failed_initialization_s"...
0x140064e1d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064e22  cmp     [r8+98h], r9b
0x140064e29  jnz     loc_1400655DF
0x140064e2f  mov     word ptr [r8+9Ah], 10h
0x140064e39  jmp     loc_140064D72
0x140064e3e  cmp     [rcx+2Ch], r11d
0x140064e42  jnz     short loc_140064E6C
0x140064e44  lea     rcx, aReasonControlF_2; "reason::control_failed_initialization_t"...
0x140064e4b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064e50  cmp     [r8+98h], r9b
0x140064e57  jnz     loc_1400655DF
0x140064e5d  mov     word ptr [r8+9Ah], 11h
0x140064e67  jmp     loc_140064D72
0x140064e6c  cmp     [rcx+30h], r11d
0x140064e70  jnz     short loc_140064E9A
0x140064e72  lea     rcx, aReasonControlF_7; "reason::control_failed_initialization_c"...
0x140064e79  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064e7e  cmp     [r8+98h], r9b
0x140064e85  jnz     loc_1400655DF
0x140064e8b  mov     word ptr [r8+9Ah], 12h
0x140064e95  jmp     loc_140064D72
0x140064e9a  cmp     [rcx+34h], r11d
0x140064e9e  jnz     short loc_140064EC8
0x140064ea0  lea     rcx, aReasonControlF_4; "reason::control_failed_initialization_s"...
0x140064ea7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064eac  cmp     [r8+98h], r9b
0x140064eb3  jnz     loc_1400655DF
0x140064eb9  mov     word ptr [r8+9Ah], 13h
0x140064ec3  jmp     loc_140064D72
0x140064ec8  cmp     [rcx+38h], r11d
0x140064ecc  jnz     short loc_140064EF6
0x140064ece  lea     rcx, aReasonControlF_5; "reason::control_failed_initialization_d"...
0x140064ed5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064eda  cmp     [r8+98h], r9b
0x140064ee1  jnz     loc_1400655DF
0x140064ee7  mov     word ptr [r8+9Ah], 14h
0x140064ef1  jmp     loc_140064D72
0x140064ef6  cmp     [rcx+3Ch], r11d
0x140064efa  jnz     short loc_140064F24
0x140064efc  lea     rcx, aReasonControlF_1; "reason::control_failed_initialization_r"...
0x140064f03  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064f08  cmp     [r8+98h], r9b
0x140064f0f  jnz     loc_1400655DF
0x140064f15  mov     word ptr [r8+9Ah], 15h
0x140064f1f  jmp     loc_140064D72
0x140064f24  cmp     [rcx+54h], r11d
0x140064f28  jnz     short loc_140064F52
0x140064f2a  lea     rcx, aReasonControlF_8; "reason::control_failed_initialization_p"...
0x140064f31  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064f36  cmp     [r8+98h], r9b
0x140064f3d  jnz     loc_1400655DF
0x140064f43  mov     word ptr [r8+9Ah], 1Bh
0x140064f4d  jmp     loc_140064D72
0x140064f52  cmp     [rcx+7Ch], r11d
0x140064f56  jnz     short loc_140064F80
0x140064f58  lea     rcx, aReasonControlF_9; "reason::control_failed_initialization_t"...
0x140064f5f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064f64  cmp     [r8+98h], r9b
0x140064f6b  jnz     loc_1400655DF
0x140064f71  mov     word ptr [r8+9Ah], 25h ; '%'
0x140064f7b  jmp     loc_140064D72
0x140064f80  mov     eax, [rcx+80h]
0x140064f86  cmp     eax, r11d
0x140064f89  jnz     short loc_140064FB3
0x140064f8b  lea     rcx, aReasonControlF_0; "reason::control_failed_initialization_t"...
0x140064f92  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064f97  cmp     [r8+98h], r9b
0x140064f9e  jnz     loc_1400655DF
0x140064fa4  mov     word ptr [r8+9Ah], 26h ; '&'
0x140064fae  jmp     loc_140064D72
0x140064fb3  cmp     [rcx+84h], r9d
0x140064fba  jnz     short loc_140064FE4
0x140064fbc  lea     rcx, aReasonFailedTo_4; "reason::failed_to_identify_taskbar_rule"
0x140064fc3  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064fc8  cmp     [r8+98h], r9b
0x140064fcf  jnz     loc_1400655DF
0x140064fd5  mov     word ptr [r8+9Ah], 5Ah ; 'Z'
0x140064fdf  jmp     loc_140064D72
0x140064fe4  cmp     [rcx+11h], r9b
0x140064fe8  jnz     short loc_140065010
0x140064fea  lea     rcx, aReasonTaskbarN; "reason::taskbar_not_created"
0x140064ff1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140064ff6  cmp     [r8+98h], r9b
0x140064ffd  jnz     loc_1400655DF
0x140065003  mov     [r8+9Ah], r11w
0x14006500b  jmp     loc_140064D72
0x140065010  cmp     [rcx+15h], r9b
0x140065014  jnz     short loc_140065052
0x140065016  lea     rcx, aReasonThemeNot; "reason::theme_not_loaded"
0x14006501d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065022  mov     r10, rax
0x140065025  cmp     [r8+98h], r9b
0x14006502c  jnz     loc_1400655DF
0x140065032  mov     eax, 3
0x140065037  mov     [r8+98h], al
0x14006503e  mov     [r8+9Ah], ax
0x140065046  mov     [r8+0A0h], r10
0x14006504d  jmp     loc_1400655DF
0x140065052  cmp     [rcx+12h], r9b
0x140065056  jnz     short loc_140065080
0x140065058  lea     rcx, aReasonFailedTo_5; "reason::failed_to_init_animations"
0x14006505f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065064  cmp     [r8+98h], r9b
0x14006506b  jnz     loc_1400655DF
0x140065071  mov     word ptr [r8+9Ah], 4
0x14006507b  jmp     loc_140064D72
0x140065080  cmp     [rcx+13h], r9b
0x140065084  jnz     short loc_1400650AE
0x140065086  lea     rcx, aReasonFailedTo_7; "reason::failed_to_init_window"
0x14006508d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065092  cmp     [r8+98h], r9b
0x140065099  jnz     loc_1400655DF
0x14006509f  mov     word ptr [r8+9Ah], 5
0x1400650a9  jmp     loc_140064D72
0x1400650ae  cmp     [rcx+14h], r9b
0x1400650b2  jnz     short loc_1400650DC
0x1400650b4  lea     rcx, aReasonPolicies; "reason::policies_not_loaded"
0x1400650bb  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400650c0  cmp     [r8+98h], r9b
0x1400650c7  jnz     loc_1400655DF
0x1400650cd  mov     word ptr [r8+9Ah], 6
0x1400650d7  jmp     loc_140064D72
0x1400650dc  cmp     [rcx+17h], r9b
0x1400650e0  jnz     short loc_14006510A
0x1400650e2  lea     rcx, aReasonCortanaS; "reason::cortana_settings_not_loaded"
0x1400650e9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400650ee  cmp     [r8+98h], r9b
0x1400650f5  jnz     loc_1400655DF
0x1400650fb  mov     word ptr [r8+9Ah], 7
0x140065105  jmp     loc_140064D72
0x14006510a  cmp     [rcx+18h], r9b
0x14006510e  jnz     short loc_140065138
0x140065110  lea     rcx, aReasonFailedTo_3; "reason::failed_to_determine_or_load_tas"...
0x140065117  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006511c  cmp     [r8+98h], r9b
0x140065123  jnz     loc_1400655DF
0x140065129  mov     word ptr [r8+9Ah], 8
0x140065133  jmp     loc_140064D72
0x140065138  cmp     [rcx+19h], r9b
0x14006513c  jnz     short loc_140065166
0x14006513e  lea     rcx, aReasonFailedTo_1; "reason::failed_to_init_taskbar_position"
0x140065145  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006514a  cmp     [r8+98h], r9b
0x140065151  jnz     loc_1400655DF
0x140065157  mov     word ptr [r8+9Ah], 9
0x140065161  jmp     loc_140064D72
0x140065166  cmp     [rcx+1Ah], r9b
0x14006516a  jnz     short loc_140065194
0x14006516c  lea     rcx, aReasonFailedTo_0; "reason::failed_to_determine_primary_tas"...
0x140065173  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065178  cmp     [r8+98h], r9b
0x14006517f  jnz     loc_1400655DF
0x140065185  mov     word ptr [r8+9Ah], 0Ah
0x14006518f  jmp     loc_140064D72
0x140065194  cmp     [rcx+20h], r9d
0x140065198  jnz     short loc_1400651C2
0x14006519a  lea     rcx, aReasonControlN_7; "reason::control_not_created_pearl"
0x1400651a1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400651a6  cmp     [r8+98h], r9b
0x1400651ad  jnz     loc_1400655DF
0x1400651b3  mov     word ptr [r8+9Ah], 40h ; '@'
0x1400651bd  jmp     loc_140064D72
0x1400651c2  cmp     [rcx+24h], r9d
0x1400651c6  jnz     short loc_1400651F0
0x1400651c8  lea     rcx, aReasonControlN_4; "reason::control_not_created_back"
0x1400651cf  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400651d4  cmp     [r8+98h], r9b
0x1400651db  jnz     loc_1400655DF
0x1400651e1  mov     word ptr [r8+9Ah], 41h ; 'A'
0x1400651eb  jmp     loc_140064D72
0x1400651f0  cmp     [rcx+28h], r9d
0x1400651f4  jnz     short loc_14006521E
0x1400651f6  lea     rcx, aReasonControlN; "reason::control_not_created_searchbutto"...
0x1400651fd  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065202  cmp     [r8+98h], r9b
0x140065209  jnz     loc_1400655DF
0x14006520f  mov     word ptr [r8+9Ah], 42h ; 'B'
0x140065219  jmp     loc_140064D72
0x14006521e  cmp     [rcx+2Ch], r9d
0x140065222  jnz     short loc_14006524C
0x140065224  lea     rcx, aReasonControlN_6; "reason::control_not_created_taskview"
0x14006522b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065230  cmp     [r8+98h], r9b
0x140065237  jnz     loc_1400655DF
0x14006523d  mov     word ptr [r8+9Ah], 43h ; 'C'
0x140065247  jmp     loc_140064D72
0x14006524c  cmp     [rcx+30h], r9d
0x140065250  jnz     short loc_14006527A
0x140065252  lea     rcx, aReasonControlN_3; "reason::control_not_created_cortana"
0x140065259  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006525e  cmp     [r8+98h], r9b
0x140065265  jnz     loc_1400655DF
0x14006526b  mov     word ptr [r8+9Ah], 44h ; 'D'
0x140065275  jmp     loc_140064D72
0x14006527a  cmp     [rcx+34h], r9d
0x14006527e  jnz     short loc_1400652A8
0x140065280  lea     rcx, aReasonControlN_5; "reason::control_not_created_searchcontr"...
0x140065287  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006528c  cmp     [r8+98h], r9b
0x140065293  jnz     loc_1400655DF
0x140065299  mov     word ptr [r8+9Ah], 45h ; 'E'
0x1400652a3  jmp     loc_140064D72
0x1400652a8  cmp     [rcx+38h], r9d
0x1400652ac  jnz     short loc_1400652D6
0x1400652ae  lea     rcx, aReasonControlN_0; "reason::control_not_created_deskbandsit"...
0x1400652b5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400652ba  cmp     [r8+98h], r9b
0x1400652c1  jnz     loc_1400655DF
0x1400652c7  mov     word ptr [r8+9Ah], 46h ; 'F'
0x1400652d1  jmp     loc_140064D72
0x1400652d6  cmp     [rcx+3Ch], r9d
0x1400652da  jnz     short loc_140065304
0x1400652dc  lea     rcx, aReasonControlN_2; "reason::control_not_created_rebar"
0x1400652e3  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400652e8  cmp     [r8+98h], r9b
0x1400652ef  jnz     loc_1400655DF
0x1400652f5  mov     word ptr [r8+9Ah], 47h ; 'G'
0x1400652ff  jmp     loc_140064D72
0x140065304  cmp     [rcx+7Ch], r9d
0x140065308  jnz     short loc_140065332
0x14006530a  lea     rcx, aReasonControlN_1; "reason::control_not_created_taskband"
0x140065311  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140065316  cmp     [r8+98h], r9b
0x14006531d  jnz     loc_1400655DF
0x140065323  mov     word ptr [r8+9Ah], 57h ; 'W'
0x14006532d  jmp     loc_140064D72
0x140065332  mov     edx, 1; char *
0x140065337  test    eax, eax
0x140065339  jnz     short loc_14006537C
0x14006533b  lea     rax, aReasonControlN_8; "reason::control_not_created_tasklist"
0x140065342  mov     cl, 72h ; 'r'
0x140065344  mov     r10, rax
0x140065347  add     rax, rdx
0x14006534a  cmp     cl, 3Ah ; ':'
0x14006534d  jnz     short loc_140065352
0x14006534f  mov     r10, rax
0x140065352  mov     cl, [rax]
0x140065354  test    cl, cl
0x140065356  jnz     short loc_140065347
0x140065358  cmp     [r8+98h], r9b
0x14006535f  jnz     loc_1400655DF
0x140065365  mov     byte ptr [r8+98h], 3
0x14006536d  mov     word ptr [r8+9Ah], 58h ; 'X'
0x140065377  jmp     loc_140065046
0x14006537c  cmp     [rcx+20h], edx
0x14006537f  jnz     short loc_1400653A9
0x140065381  lea     rcx, aReasonControlU_7; "reason::control_uninitialized_pearl"
0x140065388  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006538d  cmp     [r8+98h], r9b
0x140065394  jnz     loc_1400655DF
0x14006539a  mov     word ptr [r8+9Ah], 27h ; '''
0x1400653a4  jmp     loc_140064D72
  ... truncated ...
```
