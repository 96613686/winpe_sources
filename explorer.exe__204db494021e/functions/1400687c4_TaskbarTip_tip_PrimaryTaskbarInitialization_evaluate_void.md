# TaskbarTip::_tip_PrimaryTaskbarInitialization::evaluate(void)

- ea: `0x1400687c4`
- end: `0x140069099`
- name: `?evaluate@_tip_PrimaryTaskbarInitialization@TaskbarTip@@QEAAXXZ`
- size: `2261`
- prototype: `void __fastcall(TaskbarTip::_tip_PrimaryTaskbarInitialization *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x140132940`

## callees

- `0x1400687c4`
- `0x1400690a0`

## string_xrefs

- `0x140068def`: `reason::control_not_created_tasklist`
- `0x140068a9e`: `reason::taskbar_not_created`
- `0x140068c7c`: `reason::control_not_created_back`
- `0x140068bf2`: `reason::failed_to_init_taskbar_position`
- `0x140068d34`: `reason::control_not_created_searchcontrol`
- `0x14006904e`: `reason::taskband_accessible_title_not_set`
- `0x140068d90`: `reason::control_not_created_rebar`
- `0x140068bc4`: `reason::failed_to_determine_or_load_taskbar_placement`
- `0x140068c20`: `reason::failed_to_determine_primary_taskbar_location`
- `0x140068d62`: `reason::control_not_created_deskbandsite`
- `0x140068803`: `reason::failed_to_start_syncthread`
- `0x140068ebc`: `reason::control_uninitialized_taskview`
- `0x140068dbe`: `reason::control_not_created_taskband`
- `0x1400688f8`: `reason::control_failed_initialization_taskview`
- `0x140068cd8`: `reason::control_not_created_taskview`
- `0x140068fca`: `reason::control_uninitialized_taskband`
- `0x140068d06`: `reason::control_not_created_cortana`
- `0x140068caa`: `reason::control_not_created_searchbutton`
- `0x140068c4e`: `reason::control_not_created_pearl`
- `0x140068ff6`: `reason::control_uninitialized_tasklist`
- `0x140068a3f`: `reason::control_failed_initialization_tasklist`
- `0x140068a70`: `reason::failed_to_identify_taskbar_rule`
- `0x140068a0c`: `reason::control_failed_initialization_taskband`

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
0x1400687c4  sub     rsp, 28h
0x1400687c8  mov     r8, [rcx+8]
0x1400687cc  xor     r9d, r9d
0x1400687cf  test    dword ptr [r8+38h], 200h
0x1400687d7  jnz     short loc_1400687FD
0x1400687d9  cmp     [r8+98h], r9b
0x1400687e0  jnz     loc_140069093
0x1400687e6  mov     byte ptr [r8+98h], 3
0x1400687ee  mov     word ptr [r8+9Ah], 4001h
0x1400687f8  jmp     loc_14006908C
0x1400687fd  cmp     [rcx+10h], r9b
0x140068801  jnz     short loc_14006883A
0x140068803  lea     rcx, aReasonFailedTo_2; "reason::failed_to_start_syncthread"
0x14006880a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006880f  cmp     [r8+98h], r9b
0x140068816  jnz     loc_140069093
0x14006881c  mov     word ptr [r8+9Ah], 1
0x140068826  mov     byte ptr [r8+98h], 3
0x14006882e  mov     [r8+0A0h], rax
0x140068835  jmp     loc_140069093
0x14006883a  cmp     [rcx+1Dh], r9b
0x14006883e  jz      short loc_140068865
0x140068840  lea     rcx, aReasonFailureF; "reason::failure_from_gdi_handle_overflo"...
0x140068847  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006884c  cmp     [r8+98h], r9b
0x140068853  jnz     loc_140069093
0x140068859  mov     word ptr [r8+9Ah], 59h ; 'Y'
0x140068863  jmp     short loc_140068826
0x140068865  mov     r11d, 2
0x14006886b  cmp     [rcx+20h], r11d
0x14006886f  jnz     short loc_140068896
0x140068871  lea     rcx, aReasonControlF; "reason::control_failed_initialization_p"...
0x140068878  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006887d  cmp     [r8+98h], r9b
0x140068884  jnz     loc_140069093
0x14006888a  mov     word ptr [r8+9Ah], 0Eh
0x140068894  jmp     short loc_140068826
0x140068896  cmp     [rcx+24h], r11d
0x14006889a  jnz     short loc_1400688C4
0x14006889c  lea     rcx, aReasonControlF_6; "reason::control_failed_initialization_b"...
0x1400688a3  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400688a8  cmp     [r8+98h], r9b
0x1400688af  jnz     loc_140069093
0x1400688b5  mov     word ptr [r8+9Ah], 0Fh
0x1400688bf  jmp     loc_140068826
0x1400688c4  cmp     [rcx+28h], r11d
0x1400688c8  jnz     short loc_1400688F2
0x1400688ca  lea     rcx, aReasonControlF_3; "reason::control_failed_initialization_s"...
0x1400688d1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400688d6  cmp     [r8+98h], r9b
0x1400688dd  jnz     loc_140069093
0x1400688e3  mov     word ptr [r8+9Ah], 10h
0x1400688ed  jmp     loc_140068826
0x1400688f2  cmp     [rcx+2Ch], r11d
0x1400688f6  jnz     short loc_140068920
0x1400688f8  lea     rcx, aReasonControlF_2; "reason::control_failed_initialization_t"...
0x1400688ff  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068904  cmp     [r8+98h], r9b
0x14006890b  jnz     loc_140069093
0x140068911  mov     word ptr [r8+9Ah], 11h
0x14006891b  jmp     loc_140068826
0x140068920  cmp     [rcx+30h], r11d
0x140068924  jnz     short loc_14006894E
0x140068926  lea     rcx, aReasonControlF_7; "reason::control_failed_initialization_c"...
0x14006892d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068932  cmp     [r8+98h], r9b
0x140068939  jnz     loc_140069093
0x14006893f  mov     word ptr [r8+9Ah], 12h
0x140068949  jmp     loc_140068826
0x14006894e  cmp     [rcx+34h], r11d
0x140068952  jnz     short loc_14006897C
0x140068954  lea     rcx, aReasonControlF_4; "reason::control_failed_initialization_s"...
0x14006895b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068960  cmp     [r8+98h], r9b
0x140068967  jnz     loc_140069093
0x14006896d  mov     word ptr [r8+9Ah], 13h
0x140068977  jmp     loc_140068826
0x14006897c  cmp     [rcx+38h], r11d
0x140068980  jnz     short loc_1400689AA
0x140068982  lea     rcx, aReasonControlF_5; "reason::control_failed_initialization_d"...
0x140068989  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14006898e  cmp     [r8+98h], r9b
0x140068995  jnz     loc_140069093
0x14006899b  mov     word ptr [r8+9Ah], 14h
0x1400689a5  jmp     loc_140068826
0x1400689aa  cmp     [rcx+3Ch], r11d
0x1400689ae  jnz     short loc_1400689D8
0x1400689b0  lea     rcx, aReasonControlF_1; "reason::control_failed_initialization_r"...
0x1400689b7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400689bc  cmp     [r8+98h], r9b
0x1400689c3  jnz     loc_140069093
0x1400689c9  mov     word ptr [r8+9Ah], 15h
0x1400689d3  jmp     loc_140068826
0x1400689d8  cmp     [rcx+54h], r11d
0x1400689dc  jnz     short loc_140068A06
0x1400689de  lea     rcx, aReasonControlF_8; "reason::control_failed_initialization_p"...
0x1400689e5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400689ea  cmp     [r8+98h], r9b
0x1400689f1  jnz     loc_140069093
0x1400689f7  mov     word ptr [r8+9Ah], 1Bh
0x140068a01  jmp     loc_140068826
0x140068a06  cmp     [rcx+7Ch], r11d
0x140068a0a  jnz     short loc_140068A34
0x140068a0c  lea     rcx, aReasonControlF_9; "reason::control_failed_initialization_t"...
0x140068a13  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068a18  cmp     [r8+98h], r9b
0x140068a1f  jnz     loc_140069093
0x140068a25  mov     word ptr [r8+9Ah], 25h ; '%'
0x140068a2f  jmp     loc_140068826
0x140068a34  mov     eax, [rcx+80h]
0x140068a3a  cmp     eax, r11d
0x140068a3d  jnz     short loc_140068A67
0x140068a3f  lea     rcx, aReasonControlF_0; "reason::control_failed_initialization_t"...
0x140068a46  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068a4b  cmp     [r8+98h], r9b
0x140068a52  jnz     loc_140069093
0x140068a58  mov     word ptr [r8+9Ah], 26h ; '&'
0x140068a62  jmp     loc_140068826
0x140068a67  cmp     [rcx+84h], r9d
0x140068a6e  jnz     short loc_140068A98
0x140068a70  lea     rcx, aReasonFailedTo_4; "reason::failed_to_identify_taskbar_rule"
0x140068a77  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068a7c  cmp     [r8+98h], r9b
0x140068a83  jnz     loc_140069093
0x140068a89  mov     word ptr [r8+9Ah], 5Ah ; 'Z'
0x140068a93  jmp     loc_140068826
0x140068a98  cmp     [rcx+11h], r9b
0x140068a9c  jnz     short loc_140068AC4
0x140068a9e  lea     rcx, aReasonTaskbarN; "reason::taskbar_not_created"
0x140068aa5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068aaa  cmp     [r8+98h], r9b
0x140068ab1  jnz     loc_140069093
0x140068ab7  mov     [r8+9Ah], r11w
0x140068abf  jmp     loc_140068826
0x140068ac4  cmp     [rcx+15h], r9b
0x140068ac8  jnz     short loc_140068B06
0x140068aca  lea     rcx, aReasonThemeNot; "reason::theme_not_loaded"
0x140068ad1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068ad6  mov     r10, rax
0x140068ad9  cmp     [r8+98h], r9b
0x140068ae0  jnz     loc_140069093
0x140068ae6  mov     eax, 3
0x140068aeb  mov     [r8+98h], al
0x140068af2  mov     [r8+9Ah], ax
0x140068afa  mov     [r8+0A0h], r10
0x140068b01  jmp     loc_140069093
0x140068b06  cmp     [rcx+12h], r9b
0x140068b0a  jnz     short loc_140068B34
0x140068b0c  lea     rcx, aReasonFailedTo_5; "reason::failed_to_init_animations"
0x140068b13  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068b18  cmp     [r8+98h], r9b
0x140068b1f  jnz     loc_140069093
0x140068b25  mov     word ptr [r8+9Ah], 4
0x140068b2f  jmp     loc_140068826
0x140068b34  cmp     [rcx+13h], r9b
0x140068b38  jnz     short loc_140068B62
0x140068b3a  lea     rcx, aReasonFailedTo_7; "reason::failed_to_init_window"
0x140068b41  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068b46  cmp     [r8+98h], r9b
0x140068b4d  jnz     loc_140069093
0x140068b53  mov     word ptr [r8+9Ah], 5
0x140068b5d  jmp     loc_140068826
0x140068b62  cmp     [rcx+14h], r9b
0x140068b66  jnz     short loc_140068B90
0x140068b68  lea     rcx, aReasonPolicies; "reason::policies_not_loaded"
0x140068b6f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068b74  cmp     [r8+98h], r9b
0x140068b7b  jnz     loc_140069093
0x140068b81  mov     word ptr [r8+9Ah], 6
0x140068b8b  jmp     loc_140068826
0x140068b90  cmp     [rcx+17h], r9b
0x140068b94  jnz     short loc_140068BBE
0x140068b96  lea     rcx, aReasonCortanaS; "reason::cortana_settings_not_loaded"
0x140068b9d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068ba2  cmp     [r8+98h], r9b
0x140068ba9  jnz     loc_140069093
0x140068baf  mov     word ptr [r8+9Ah], 7
0x140068bb9  jmp     loc_140068826
0x140068bbe  cmp     [rcx+18h], r9b
0x140068bc2  jnz     short loc_140068BEC
0x140068bc4  lea     rcx, aReasonFailedTo_3; "reason::failed_to_determine_or_load_tas"...
0x140068bcb  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068bd0  cmp     [r8+98h], r9b
0x140068bd7  jnz     loc_140069093
0x140068bdd  mov     word ptr [r8+9Ah], 8
0x140068be7  jmp     loc_140068826
0x140068bec  cmp     [rcx+19h], r9b
0x140068bf0  jnz     short loc_140068C1A
0x140068bf2  lea     rcx, aReasonFailedTo_1; "reason::failed_to_init_taskbar_position"
0x140068bf9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068bfe  cmp     [r8+98h], r9b
0x140068c05  jnz     loc_140069093
0x140068c0b  mov     word ptr [r8+9Ah], 9
0x140068c15  jmp     loc_140068826
0x140068c1a  cmp     [rcx+1Ah], r9b
0x140068c1e  jnz     short loc_140068C48
0x140068c20  lea     rcx, aReasonFailedTo_0; "reason::failed_to_determine_primary_tas"...
0x140068c27  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068c2c  cmp     [r8+98h], r9b
0x140068c33  jnz     loc_140069093
0x140068c39  mov     word ptr [r8+9Ah], 0Ah
0x140068c43  jmp     loc_140068826
0x140068c48  cmp     [rcx+20h], r9d
0x140068c4c  jnz     short loc_140068C76
0x140068c4e  lea     rcx, aReasonControlN_7; "reason::control_not_created_pearl"
0x140068c55  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068c5a  cmp     [r8+98h], r9b
0x140068c61  jnz     loc_140069093
0x140068c67  mov     word ptr [r8+9Ah], 40h ; '@'
0x140068c71  jmp     loc_140068826
0x140068c76  cmp     [rcx+24h], r9d
0x140068c7a  jnz     short loc_140068CA4
0x140068c7c  lea     rcx, aReasonControlN_4; "reason::control_not_created_back"
0x140068c83  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068c88  cmp     [r8+98h], r9b
0x140068c8f  jnz     loc_140069093
0x140068c95  mov     word ptr [r8+9Ah], 41h ; 'A'
0x140068c9f  jmp     loc_140068826
0x140068ca4  cmp     [rcx+28h], r9d
0x140068ca8  jnz     short loc_140068CD2
0x140068caa  lea     rcx, aReasonControlN; "reason::control_not_created_searchbutto"...
0x140068cb1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068cb6  cmp     [r8+98h], r9b
0x140068cbd  jnz     loc_140069093
0x140068cc3  mov     word ptr [r8+9Ah], 42h ; 'B'
0x140068ccd  jmp     loc_140068826
0x140068cd2  cmp     [rcx+2Ch], r9d
0x140068cd6  jnz     short loc_140068D00
0x140068cd8  lea     rcx, aReasonControlN_6; "reason::control_not_created_taskview"
0x140068cdf  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068ce4  cmp     [r8+98h], r9b
0x140068ceb  jnz     loc_140069093
0x140068cf1  mov     word ptr [r8+9Ah], 43h ; 'C'
0x140068cfb  jmp     loc_140068826
0x140068d00  cmp     [rcx+30h], r9d
0x140068d04  jnz     short loc_140068D2E
0x140068d06  lea     rcx, aReasonControlN_3; "reason::control_not_created_cortana"
0x140068d0d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068d12  cmp     [r8+98h], r9b
0x140068d19  jnz     loc_140069093
0x140068d1f  mov     word ptr [r8+9Ah], 44h ; 'D'
0x140068d29  jmp     loc_140068826
0x140068d2e  cmp     [rcx+34h], r9d
0x140068d32  jnz     short loc_140068D5C
0x140068d34  lea     rcx, aReasonControlN_5; "reason::control_not_created_searchcontr"...
0x140068d3b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068d40  cmp     [r8+98h], r9b
0x140068d47  jnz     loc_140069093
0x140068d4d  mov     word ptr [r8+9Ah], 45h ; 'E'
0x140068d57  jmp     loc_140068826
0x140068d5c  cmp     [rcx+38h], r9d
0x140068d60  jnz     short loc_140068D8A
0x140068d62  lea     rcx, aReasonControlN_0; "reason::control_not_created_deskbandsit"...
0x140068d69  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068d6e  cmp     [r8+98h], r9b
0x140068d75  jnz     loc_140069093
0x140068d7b  mov     word ptr [r8+9Ah], 46h ; 'F'
0x140068d85  jmp     loc_140068826
0x140068d8a  cmp     [rcx+3Ch], r9d
0x140068d8e  jnz     short loc_140068DB8
0x140068d90  lea     rcx, aReasonControlN_2; "reason::control_not_created_rebar"
0x140068d97  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068d9c  cmp     [r8+98h], r9b
0x140068da3  jnz     loc_140069093
0x140068da9  mov     word ptr [r8+9Ah], 47h ; 'G'
0x140068db3  jmp     loc_140068826
0x140068db8  cmp     [rcx+7Ch], r9d
0x140068dbc  jnz     short loc_140068DE6
0x140068dbe  lea     rcx, aReasonControlN_1; "reason::control_not_created_taskband"
0x140068dc5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068dca  cmp     [r8+98h], r9b
0x140068dd1  jnz     loc_140069093
0x140068dd7  mov     word ptr [r8+9Ah], 57h ; 'W'
0x140068de1  jmp     loc_140068826
0x140068de6  mov     edx, 1; char *
0x140068deb  test    eax, eax
0x140068ded  jnz     short loc_140068E30
0x140068def  lea     rax, aReasonControlN_8; "reason::control_not_created_tasklist"
0x140068df6  mov     cl, 72h ; 'r'
0x140068df8  mov     r10, rax
0x140068dfb  add     rax, rdx
0x140068dfe  cmp     cl, 3Ah ; ':'
0x140068e01  jnz     short loc_140068E06
0x140068e03  mov     r10, rax
0x140068e06  mov     cl, [rax]
0x140068e08  test    cl, cl
0x140068e0a  jnz     short loc_140068DFB
0x140068e0c  cmp     [r8+98h], r9b
0x140068e13  jnz     loc_140069093
0x140068e19  mov     byte ptr [r8+98h], 3
0x140068e21  mov     word ptr [r8+9Ah], 58h ; 'X'
0x140068e2b  jmp     loc_140068AFA
0x140068e30  cmp     [rcx+20h], edx
0x140068e33  jnz     short loc_140068E5D
0x140068e35  lea     rcx, aReasonControlU_7; "reason::control_uninitialized_pearl"
0x140068e3c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140068e41  cmp     [r8+98h], r9b
0x140068e48  jnz     loc_140069093
0x140068e4e  mov     word ptr [r8+9Ah], 27h ; '''
0x140068e58  jmp     loc_140068826
  ... truncated ...
```
