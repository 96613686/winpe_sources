# APP_POOL_DATA_OBJECT::Clone(void)

- ea: `0x180037a30`
- end: `0x180038307`
- name: `?Clone@APP_POOL_DATA_OBJECT@@UEAAPEAVDATA_OBJECT@@XZ`
- size: `2263`
- prototype: `struct DATA_OBJECT *__fastcall(APP_POOL_DATA_OBJECT *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001234`
- `0x1800376c0`
- `0x180037a30`
- `0x1800539a0`
- `0x180062010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800382d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800382d9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800382a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800382a8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180038297`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180038297`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800382b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800382b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003827d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003827d`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180037a77`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180037a77`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038137`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18003814f`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038167`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18003817f`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18003819b`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800381b7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800381d3`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800381fb`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038217`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038233`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038137`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18003814f`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038167`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18003817f`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18003819b`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800381b7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800381d3`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800381fb`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038217`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180038233`
- `iisutil!?Clone@MULTISZ@@QEBAHPEAV1@@Z` at `0x1800380fa`
- `iisutil!?Clone@MULTISZ@@QEBAHPEAV1@@Z` at `0x1800380fa`

## pseudocode

```c
struct DATA_OBJECT *__fastcall APP_POOL_DATA_OBJECT::Clone(APP_POOL_DATA_OBJECT *this)
{
  APP_POOL_DATA_OBJECT *v2; // rax
  APP_POOL_DATA_OBJECT *v3; // rax
  APP_POOL_DATA_OBJECT *v4; // rbx
  int v5; // ecx
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  int v32; // eax
  int v33; // edx
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  int v40; // ecx
  int v41; // eax
  int v42; // ecx
  int v43; // eax
  int v44; // ecx
  int v45; // eax
  int v46; // ecx
  int v47; // eax
  int v48; // ecx
  int v49; // eax
  int v50; // ecx
  int v51; // eax
  int v52; // ecx
  int v53; // eax
  int v54; // ecx
  int v55; // eax
  int v56; // ecx
  int v57; // eax
  int v58; // ecx
  void *v60; // rcx
  DWORD LengthSid; // esi
  HLOCAL v62; // rax

  v2 = (APP_POOL_DATA_OBJECT *)operator new(0x408u);
  if ( !v2 )
    return 0;
  v3 = APP_POOL_DATA_OBJECT::APP_POOL_DATA_OBJECT(v2);
  v4 = v3;
  if ( !v3 )
    return 0;
  MULTISZ::Copy((APP_POOL_DATA_OBJECT *)((char *)v3 + 936), (APP_POOL_DATA_OBJECT *)((char *)this + 936));
  *((_DWORD *)v4 + 26) = *((_DWORD *)this + 26);
  *((_DWORD *)v4 + 27) = *((_DWORD *)this + 27);
  *((_DWORD *)v4 + 28) = *((_DWORD *)this + 28);
  *((_DWORD *)v4 + 29) = *((_DWORD *)this + 29);
  *((_DWORD *)v4 + 44) = *((_DWORD *)this + 44);
  *((_DWORD *)v4 + 47) = *((_DWORD *)this + 47);
  *((_DWORD *)v4 + 45) = *((_DWORD *)this + 45);
  *((_DWORD *)v4 + 46) = *((_DWORD *)this + 46);
  *((_DWORD *)v4 + 48) = *((_DWORD *)this + 48);
  *((_DWORD *)v4 + 49) = *((_DWORD *)this + 49);
  *((_DWORD *)v4 + 50) = *((_DWORD *)this + 50);
  *((_DWORD *)v4 + 51) = *((_DWORD *)this + 51);
  *((_DWORD *)v4 + 52) = *((_DWORD *)this + 52);
  *((_DWORD *)v4 + 53) = *((_DWORD *)this + 53);
  *((_DWORD *)v4 + 54) = *((_DWORD *)this + 54);
  *((_DWORD *)v4 + 55) = *((_DWORD *)this + 55);
  *((_DWORD *)v4 + 56) = *((_DWORD *)this + 56);
  *((_DWORD *)v4 + 57) = *((_DWORD *)this + 57);
  *((_DWORD *)v4 + 58) = *((_DWORD *)this + 58);
  *((_DWORD *)v4 + 59) = *((_DWORD *)this + 59);
  *((_DWORD *)v4 + 60) = *((_DWORD *)this + 60);
  *((_DWORD *)v4 + 90) = *((_DWORD *)this + 90);
  *((_DWORD *)v4 + 91) = *((_DWORD *)this + 91);
  *((_DWORD *)v4 + 144) = *((_DWORD *)this + 144);
  *((_DWORD *)v4 + 145) = *((_DWORD *)this + 145);
  *((_DWORD *)v4 + 146) = *((_DWORD *)this + 146);
  *((_DWORD *)v4 + 147) = *((_DWORD *)this + 147);
  *((_DWORD *)v4 + 148) = *((_DWORD *)this + 148);
  *((_DWORD *)v4 + 149) = *((_DWORD *)this + 149);
  *((_DWORD *)v4 + 150) = *((_DWORD *)this + 150);
  *((_DWORD *)v4 + 151) = *((_DWORD *)this + 151);
  *((_DWORD *)v4 + 180) = *((_DWORD *)this + 180);
  *((_DWORD *)v4 + 181) = *((_DWORD *)this + 181);
  *((_DWORD *)v4 + 182) = *((_DWORD *)this + 182);
  *((_DWORD *)v4 + 183) = *((_DWORD *)this + 183);
  *((_DWORD *)v4 + 184) = *((_DWORD *)this + 184);
  *((_DWORD *)v4 + 229) = *((_DWORD *)this + 229);
  *((_DWORD *)v4 + 230) = *((_DWORD *)this + 230);
  *((_DWORD *)v4 + 231) = *((_DWORD *)this + 231);
  *((_DWORD *)v4 + 232) = *((_DWORD *)this + 232);
  *((_DWORD *)v4 + 233) = *((_DWORD *)this + 233);
  v5 = *((_DWORD *)v4 + 254) ^ (*((_DWORD *)this + 254) ^ *((_DWORD *)v4 + 254)) & 1;
  *((_DWORD *)v4 + 254) = v5;
  v6 = v5 ^ (*((_DWORD *)this + 254) ^ v5) & 2;
  *((_DWORD *)v4 + 254) = v6;
  v7 = v6 ^ (*((_DWORD *)this + 254) ^ v6) & 4;
  *((_DWORD *)v4 + 254) = v7;
  v8 = v7 ^ (*((_DWORD *)this + 254) ^ v7) & 8;
  *((_DWORD *)v4 + 254) = v8;
  v9 = v8 ^ (*((_DWORD *)this + 254) ^ v8) & 0x10;
  *((_DWORD *)v4 + 254) = v9;
  v10 = v9 ^ (*((_DWORD *)this + 254) ^ v9) & 0x20;
  *((_DWORD *)v4 + 254) = v10;
  v11 = v10 ^ (*((_DWORD *)this + 254) ^ v10) & 0x40;
  *((_DWORD *)v4 + 254) = v11;
  v12 = v11 ^ (*((_DWORD *)this + 254) ^ v11) & 0x80;
  *((_DWORD *)v4 + 254) = v12;
  v13 = v12 ^ (*((_DWORD *)this + 254) ^ v12) & 0x100;
  *((_DWORD *)v4 + 254) = v13;
  v14 = v13 ^ (*((_DWORD *)this + 254) ^ v13) & 0x200;
  *((_DWORD *)v4 + 254) = v14;
  v15 = v14 ^ (*((_DWORD *)this + 254) ^ v14) & 0x400;
  *((_DWORD *)v4 + 254) = v15;
  v16 = v15 ^ (*((_DWORD *)this + 254) ^ v15) & 0x800;
  *((_DWORD *)v4 + 254) = v16;
  v17 = v16 ^ (*((_DWORD *)this + 254) ^ v16) & 0x1000;
  *((_DWORD *)v4 + 254) = v17;
  v18 = v17 ^ (*((_DWORD *)this + 254) ^ v17) & 0x2000;
  *((_DWORD *)v4 + 254) = v18;
  v19 = v18 ^ (*((_DWORD *)this + 254) ^ v18) & 0x4000;
  *((_DWORD *)v4 + 254) = v19;
  v20 = v19 ^ (*((_DWORD *)this + 254) ^ v19) & 0x8000;
  *((_DWORD *)v4 + 254) = v20;
  v21 = v20 ^ (*((_DWORD *)this + 254) ^ v20) & 0x10000;
  *((_DWORD *)v4 + 254) = v21;
  v22 = v21 ^ (*((_DWORD *)this + 254) ^ v21) & 0x20000;
  *((_DWORD *)v4 + 254) = v22;
  v23 = v22 ^ (*((_DWORD *)this + 254) ^ v22) & 0x40000;
  *((_DWORD *)v4 + 254) = v23;
  v24 = v23 ^ (*((_DWORD *)this + 254) ^ v23) & 0x80000;
  *((_DWORD *)v4 + 254) = v24;
  v25 = v24 ^ (*((_DWORD *)this + 254) ^ v24) & 0x100000;
  *((_DWORD *)v4 + 254) = v25;
  v26 = v25 ^ (*((_DWORD *)this + 254) ^ v25) & 0x200000;
  *((_DWORD *)v4 + 254) = v26;
  v27 = v26 ^ (*((_DWORD *)this + 254) ^ v26) & 0x400000;
  *((_DWORD *)v4 + 254) = v27;
  v28 = v27 ^ (*((_DWORD *)this + 254) ^ v27) & 0x800000;
  *((_DWORD *)v4 + 254) = v28;
  v29 = v28 ^ (*((_DWORD *)this + 254) ^ v28) & 0x1000000;
  *((_DWORD *)v4 + 254) = v29;
  v30 = v29 ^ (*((_DWORD *)this + 254) ^ v29) & 0x2000000;
  *((_DWORD *)v4 + 254) = v30;
  v31 = v30 ^ (*((_DWORD *)this + 254) ^ v30) & 0x4000000;
  *((_DWORD *)v4 + 254) = v31;
  v32 = v31 ^ (*((_DWORD *)this + 254) ^ v31) & 0x8000000;
  *((_DWORD *)v4 + 254) = v32;
  v33 = v32 ^ (*((_DWORD *)this + 254) ^ v32) & 0x10000000;
  v34 = *((_DWORD *)v4 + 255);
  *((_DWORD *)v4 + 254) = v33;
  v35 = v34 ^ (*((_DWORD *)this + 255) ^ v34) & 0x200000;
  *((_DWORD *)v4 + 255) = v35;
  v36 = v35 ^ (*((_DWORD *)this + 255) ^ v35) & 0x400000;
  *((_DWORD *)v4 + 255) = v36;
  v37 = v33 ^ (*((_DWORD *)this + 254) ^ v33) & 0x20000000;
  *((_DWORD *)v4 + 254) = v37;
  v38 = v37 ^ (*((_DWORD *)this + 254) ^ v37) & 0x40000000;
  *((_DWORD *)v4 + 254) = v38;
  *((_DWORD *)v4 + 254) = *((_DWORD *)this + 254) ^ (*((_DWORD *)this + 254) ^ v38) & 0x7FFFFFFF;
  v39 = v36 ^ (*((_DWORD *)this + 255) ^ v36) & 1;
  *((_DWORD *)v4 + 255) = v39;
  v40 = v39 ^ (*((_DWORD *)this + 255) ^ v39) & 2;
  *((_DWORD *)v4 + 255) = v40;
  v41 = v40 ^ (*((_DWORD *)this + 255) ^ v40) & 4;
  *((_DWORD *)v4 + 255) = v41;
  v42 = v41 ^ (*((_DWORD *)this + 255) ^ v41) & 8;
  *((_DWORD *)v4 + 255) = v42;
  v43 = v42 ^ (*((_DWORD *)this + 255) ^ v42) & 0x10;
  *((_DWORD *)v4 + 255) = v43;
  v44 = v43 ^ (*((_DWORD *)this + 255) ^ v43) & 0x20;
  *((_DWORD *)v4 + 255) = v44;
  v45 = v44 ^ (*((_DWORD *)this + 255) ^ v44) & 0x40;
  *((_DWORD *)v4 + 255) = v45;
  v46 = v45 ^ (*((_DWORD *)this + 255) ^ v45) & 0x80;
  *((_DWORD *)v4 + 255) = v46;
  v47 = v46 ^ (*((_DWORD *)this + 255) ^ v46) & 0x100;
  *((_DWORD *)v4 + 255) = v47;
  v48 = v47 ^ (*((_DWORD *)this + 255) ^ v47) & 0x200;
  *((_DWORD *)v4 + 255) = v48;
  v49 = v48 ^ (*((_DWORD *)this + 255) ^ v48) & 0x400;
  *((_DWORD *)v4 + 255) = v49;
  v50 = v49 ^ (*((_DWORD *)this + 255) ^ v49) & 0x800;
  *((_DWORD *)v4 + 255) = v50;
  v51 = v50 ^ (*((_DWORD *)this + 255) ^ v50) & 0x1000;
  *((_DWORD *)v4 + 255) = v51;
  v52 = v51 ^ (*((_DWORD *)this + 255) ^ v51) & 0x2000;
  *((_DWORD *)v4 + 255) = v52;
  v53 = v52 ^ (*((_DWORD *)this + 255) ^ v52) & 0x4000;
  *((_DWORD *)v4 + 255) = v53;
  v54 = v53 ^ (*((_DWORD *)this + 255) ^ v53) & 0x8000;
  *((_DWORD *)v4 + 255) = v54;
  v55 = v54 ^ (*((_DWORD *)this + 255) ^ v54) & 0x10000;
  *((_DWORD *)v4 + 255) = v55;
  v56 = v55 ^ (*((_DWORD *)this + 255) ^ v55) & 0x20000;
  *((_DWORD *)v4 + 255) = v56;
  v57 = v56 ^ (*((_DWORD *)this + 255) ^ v56) & 0x40000;
  *((_DWORD *)v4 + 255) = v57;
  v58 = v57 ^ (*((_DWORD *)this + 255) ^ v57) & 0x80000;
  *((_DWORD *)v4 + 255) = v58;
  *((_DWORD *)v4 + 255) = v58 ^ (*((_DWORD *)this + 255) ^ v58) & 0x100000;
  CONFIG_ERROR_LIST::Clone((APP_POOL_DATA_OBJECT *)((char *)v4 + 1000), (APP_POOL_DATA_OBJECT *)((char *)this + 1000));
  if ( !MULTISZ::Clone((APP_POOL_DATA_OBJECT *)((char *)this + 120), (APP_POOL_DATA_OBJECT *)((char *)v4 + 120))
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 248), (APP_POOL_DATA_OBJECT *)((char *)this + 248)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 304), (APP_POOL_DATA_OBJECT *)((char *)this + 304)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 608), (APP_POOL_DATA_OBJECT *)((char *)this + 608)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 664), (APP_POOL_DATA_OBJECT *)((char *)this + 664)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 744), (APP_POOL_DATA_OBJECT *)((char *)this + 744)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 800), (APP_POOL_DATA_OBJECT *)((char *)this + 800)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 856), (APP_POOL_DATA_OBJECT *)((char *)this + 856)) < 0
    || (*((_DWORD *)v4 + 228) = *((_DWORD *)this + 228),
        (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 368), (APP_POOL_DATA_OBJECT *)((char *)this + 368)) < 0)
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 424), (APP_POOL_DATA_OBJECT *)((char *)this + 424)) < 0
    || (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 480), (APP_POOL_DATA_OBJECT *)((char *)this + 480)) < 0
    || (*((_DWORD *)v4 + 134) = *((_DWORD *)this + 134),
        *((_DWORD *)v4 + 135) = *((_DWORD *)this + 135),
        *((_OWORD *)v4 + 34) = *((_OWORD *)this + 34),
        *((_OWORD *)v4 + 35) = *((_OWORD *)this + 35),
        (int)STRU::Copy((APP_POOL_DATA_OBJECT *)((char *)v4 + 48), *((const unsigned __int16 **)this + 10)) < 0) )
  {
    (**(void (__fastcall ***)(APP_POOL_DATA_OBJECT *, __int64))v4)(v4, 1);
    return 0;
  }
  v60 = (void *)*((_QWORD *)this + 124);
  if ( v60 )
  {
    if ( IsValidSid(v60) )
    {
      LengthSid = GetLengthSid(*((PSID *)this + 124));
      v62 = LocalAlloc(0x40u, LengthSid);
      *((_QWORD *)v4 + 124) = v62;
      if ( !v62 || !CopySid(LengthSid, v62, *((PSID *)this + 124)) )
        return 0;
    }
  }
  *((_DWORD *)v4 + 4) = *((_DWORD *)this + 4);
  *((_DWORD *)v4 + 5) = *((_DWORD *)this + 5);
  *((_DWORD *)v4 + 7) = *((_DWORD *)this + 7);
  *((_DWORD *)v4 + 6) = *((_DWORD *)this + 6);
  return v4;
}

```

## disassembly

```asm
0x180037a30  mov     [rsp+arg_0], rbx
0x180037a35  mov     [rsp+arg_8], rsi
0x180037a3a  push    rdi
0x180037a3b  sub     rsp, 20h
0x180037a3f  mov     rdi, rcx
0x180037a42  mov     ecx, 408h; Size
0x180037a47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037a4c  test    rax, rax
0x180037a4f  jz      loc_180038117
0x180037a55  mov     rcx, rax; this
0x180037a58  call    ??0APP_POOL_DATA_OBJECT@@QEAA@XZ; APP_POOL_DATA_OBJECT::APP_POOL_DATA_OBJECT(void)
0x180037a5d  mov     rbx, rax
0x180037a60  test    rax, rax
0x180037a63  jz      loc_180038117
0x180037a69  lea     rdx, [rdi+3A8h]
0x180037a70  lea     rcx, [rax+3A8h]
0x180037a77  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x180037a7d  mov     ecx, [rdi+68h]
0x180037a80  mov     [rbx+68h], ecx
0x180037a83  mov     ecx, [rdi+6Ch]
0x180037a86  mov     [rbx+6Ch], ecx
0x180037a89  mov     ecx, [rdi+70h]
0x180037a8c  mov     [rbx+70h], ecx
0x180037a8f  mov     ecx, [rdi+74h]
0x180037a92  mov     [rbx+74h], ecx
0x180037a95  mov     eax, [rdi+0B0h]
0x180037a9b  mov     [rbx+0B0h], eax
0x180037aa1  mov     eax, [rdi+0BCh]
0x180037aa7  mov     [rbx+0BCh], eax
0x180037aad  mov     eax, [rdi+0B4h]
0x180037ab3  mov     [rbx+0B4h], eax
0x180037ab9  mov     eax, [rdi+0B8h]
0x180037abf  mov     [rbx+0B8h], eax
0x180037ac5  mov     eax, [rdi+0C0h]
0x180037acb  mov     [rbx+0C0h], eax
0x180037ad1  mov     eax, [rdi+0C4h]
0x180037ad7  mov     [rbx+0C4h], eax
0x180037add  mov     eax, [rdi+0C8h]
0x180037ae3  mov     [rbx+0C8h], eax
0x180037ae9  mov     eax, [rdi+0CCh]
0x180037aef  mov     [rbx+0CCh], eax
0x180037af5  mov     eax, [rdi+0D0h]
0x180037afb  mov     [rbx+0D0h], eax
0x180037b01  mov     eax, [rdi+0D4h]
0x180037b07  mov     [rbx+0D4h], eax
0x180037b0d  mov     eax, [rdi+0D8h]
0x180037b13  mov     [rbx+0D8h], eax
0x180037b19  mov     eax, [rdi+0DCh]
0x180037b1f  mov     [rbx+0DCh], eax
0x180037b25  mov     eax, [rdi+0E0h]
0x180037b2b  mov     [rbx+0E0h], eax
0x180037b31  mov     eax, [rdi+0E4h]
0x180037b37  mov     [rbx+0E4h], eax
0x180037b3d  mov     eax, [rdi+0E8h]
0x180037b43  mov     [rbx+0E8h], eax
0x180037b49  mov     eax, [rdi+0ECh]
0x180037b4f  mov     [rbx+0ECh], eax
0x180037b55  mov     eax, [rdi+0F0h]
0x180037b5b  mov     [rbx+0F0h], eax
0x180037b61  mov     eax, [rdi+168h]
0x180037b67  mov     [rbx+168h], eax
0x180037b6d  mov     eax, [rdi+16Ch]
0x180037b73  mov     [rbx+16Ch], eax
0x180037b79  mov     eax, [rdi+240h]
0x180037b7f  mov     [rbx+240h], eax
0x180037b85  mov     eax, [rdi+244h]
0x180037b8b  mov     [rbx+244h], eax
0x180037b91  mov     eax, [rdi+248h]
0x180037b97  mov     [rbx+248h], eax
0x180037b9d  mov     eax, [rdi+24Ch]
0x180037ba3  mov     [rbx+24Ch], eax
0x180037ba9  mov     eax, [rdi+250h]
0x180037baf  mov     [rbx+250h], eax
0x180037bb5  mov     eax, [rdi+254h]
0x180037bbb  mov     [rbx+254h], eax
0x180037bc1  mov     eax, [rdi+258h]
0x180037bc7  mov     [rbx+258h], eax
0x180037bcd  mov     eax, [rdi+25Ch]
0x180037bd3  mov     [rbx+25Ch], eax
0x180037bd9  mov     eax, [rdi+2D0h]
0x180037bdf  mov     [rbx+2D0h], eax
0x180037be5  mov     eax, [rdi+2D4h]
0x180037beb  mov     [rbx+2D4h], eax
0x180037bf1  mov     eax, [rdi+2D8h]
0x180037bf7  mov     [rbx+2D8h], eax
0x180037bfd  mov     eax, [rdi+2DCh]
0x180037c03  mov     [rbx+2DCh], eax
0x180037c09  mov     eax, [rdi+2E0h]
0x180037c0f  mov     [rbx+2E0h], eax
0x180037c15  mov     eax, [rdi+394h]
0x180037c1b  mov     [rbx+394h], eax
0x180037c21  mov     eax, [rdi+398h]
0x180037c27  mov     [rbx+398h], eax
0x180037c2d  mov     eax, [rdi+39Ch]
0x180037c33  mov     [rbx+39Ch], eax
0x180037c39  mov     eax, [rdi+3A0h]
0x180037c3f  mov     [rbx+3A0h], eax
0x180037c45  mov     eax, [rdi+3A4h]
0x180037c4b  mov     [rbx+3A4h], eax
0x180037c51  mov     eax, [rbx+3F8h]
0x180037c57  mov     ecx, eax
0x180037c59  xor     ecx, [rdi+3F8h]
0x180037c5f  and     ecx, 1
0x180037c62  xor     ecx, eax
0x180037c64  mov     [rbx+3F8h], ecx
0x180037c6a  mov     eax, ecx
0x180037c6c  xor     eax, [rdi+3F8h]
0x180037c72  and     eax, 2
0x180037c75  xor     eax, ecx
0x180037c77  mov     [rbx+3F8h], eax
0x180037c7d  mov     ecx, eax
0x180037c7f  xor     ecx, [rdi+3F8h]
0x180037c85  and     ecx, 4
0x180037c88  xor     ecx, eax
0x180037c8a  mov     [rbx+3F8h], ecx
0x180037c90  mov     eax, ecx
0x180037c92  xor     eax, [rdi+3F8h]
0x180037c98  and     eax, 8
0x180037c9b  xor     eax, ecx
0x180037c9d  mov     [rbx+3F8h], eax
0x180037ca3  mov     ecx, eax
0x180037ca5  xor     ecx, [rdi+3F8h]
0x180037cab  and     ecx, 10h
0x180037cae  xor     ecx, eax
0x180037cb0  mov     [rbx+3F8h], ecx
0x180037cb6  mov     eax, ecx
0x180037cb8  xor     eax, [rdi+3F8h]
0x180037cbe  and     eax, 20h
0x180037cc1  xor     eax, ecx
0x180037cc3  mov     [rbx+3F8h], eax
0x180037cc9  mov     ecx, eax
0x180037ccb  xor     ecx, [rdi+3F8h]
0x180037cd1  and     ecx, 40h
0x180037cd4  xor     ecx, eax
0x180037cd6  mov     [rbx+3F8h], ecx
0x180037cdc  mov     eax, ecx
0x180037cde  xor     eax, [rdi+3F8h]
0x180037ce4  and     eax, 80h
0x180037ce9  xor     eax, ecx
0x180037ceb  mov     [rbx+3F8h], eax
0x180037cf1  mov     ecx, eax
0x180037cf3  xor     ecx, [rdi+3F8h]
0x180037cf9  and     ecx, 100h
0x180037cff  xor     ecx, eax
0x180037d01  mov     [rbx+3F8h], ecx
0x180037d07  mov     eax, ecx
0x180037d09  xor     eax, [rdi+3F8h]
0x180037d0f  and     eax, 200h
0x180037d14  xor     eax, ecx
0x180037d16  mov     [rbx+3F8h], eax
0x180037d1c  mov     ecx, eax
0x180037d1e  xor     ecx, [rdi+3F8h]
0x180037d24  and     ecx, 400h
0x180037d2a  xor     ecx, eax
0x180037d2c  mov     [rbx+3F8h], ecx
0x180037d32  mov     eax, ecx
0x180037d34  xor     eax, [rdi+3F8h]
0x180037d3a  and     eax, 800h
0x180037d3f  xor     eax, ecx
0x180037d41  mov     [rbx+3F8h], eax
0x180037d47  mov     ecx, eax
0x180037d49  xor     ecx, [rdi+3F8h]
0x180037d4f  and     ecx, 1000h
0x180037d55  xor     ecx, eax
0x180037d57  mov     [rbx+3F8h], ecx
0x180037d5d  mov     eax, ecx
0x180037d5f  xor     eax, [rdi+3F8h]
0x180037d65  and     eax, 2000h
0x180037d6a  xor     eax, ecx
0x180037d6c  mov     [rbx+3F8h], eax
0x180037d72  mov     ecx, eax
0x180037d74  xor     ecx, [rdi+3F8h]
0x180037d7a  and     ecx, 4000h
0x180037d80  xor     ecx, eax
0x180037d82  mov     [rbx+3F8h], ecx
0x180037d88  mov     eax, ecx
0x180037d8a  xor     eax, [rdi+3F8h]
0x180037d90  mov     r8d, 200000h
0x180037d96  and     eax, 8000h
0x180037d9b  mov     esi, 40000h
0x180037da0  xor     eax, ecx
0x180037da2  mov     r11d, 80000h
0x180037da8  mov     [rbx+3F8h], eax
0x180037dae  mov     ecx, eax
0x180037db0  xor     ecx, [rdi+3F8h]
0x180037db6  mov     r10d, 100000h
0x180037dbc  and     ecx, 10000h
0x180037dc2  mov     r9d, 400000h
0x180037dc8  xor     ecx, eax
0x180037dca  mov     [rbx+3F8h], ecx
0x180037dd0  mov     eax, ecx
0x180037dd2  xor     eax, [rdi+3F8h]
0x180037dd8  and     eax, 20000h
0x180037ddd  xor     eax, ecx
0x180037ddf  mov     [rbx+3F8h], eax
0x180037de5  mov     ecx, eax
0x180037de7  xor     ecx, [rdi+3F8h]
0x180037ded  and     ecx, esi
0x180037def  xor     ecx, eax
0x180037df1  mov     [rbx+3F8h], ecx
0x180037df7  mov     eax, ecx
0x180037df9  xor     eax, [rdi+3F8h]
0x180037dff  and     eax, r11d
0x180037e02  xor     eax, ecx
0x180037e04  mov     [rbx+3F8h], eax
0x180037e0a  mov     ecx, eax
0x180037e0c  xor     ecx, [rdi+3F8h]
0x180037e12  and     ecx, r10d
0x180037e15  xor     ecx, eax
0x180037e17  mov     [rbx+3F8h], ecx
0x180037e1d  mov     eax, ecx
0x180037e1f  xor     eax, [rdi+3F8h]
0x180037e25  and     eax, r8d
0x180037e28  xor     eax, ecx
0x180037e2a  mov     [rbx+3F8h], eax
0x180037e30  mov     ecx, eax
0x180037e32  xor     ecx, [rdi+3F8h]
0x180037e38  and     ecx, r9d
0x180037e3b  xor     ecx, eax
0x180037e3d  mov     [rbx+3F8h], ecx
0x180037e43  mov     eax, ecx
0x180037e45  xor     eax, [rdi+3F8h]
0x180037e4b  and     eax, 800000h
0x180037e50  xor     eax, ecx
0x180037e52  mov     [rbx+3F8h], eax
0x180037e58  mov     ecx, eax
0x180037e5a  xor     ecx, [rdi+3F8h]
0x180037e60  and     ecx, 1000000h
0x180037e66  xor     ecx, eax
0x180037e68  mov     [rbx+3F8h], ecx
0x180037e6e  mov     eax, ecx
0x180037e70  xor     eax, [rdi+3F8h]
0x180037e76  and     eax, 2000000h
0x180037e7b  xor     eax, ecx
0x180037e7d  mov     [rbx+3F8h], eax
0x180037e83  mov     ecx, eax
0x180037e85  xor     ecx, [rdi+3F8h]
0x180037e8b  and     ecx, 4000000h
0x180037e91  xor     ecx, eax
0x180037e93  mov     [rbx+3F8h], ecx
0x180037e99  mov     eax, ecx
0x180037e9b  xor     eax, [rdi+3F8h]
0x180037ea1  and     eax, 8000000h
0x180037ea6  xor     eax, ecx
0x180037ea8  mov     [rbx+3F8h], eax
0x180037eae  mov     edx, eax
0x180037eb0  xor     edx, [rdi+3F8h]
0x180037eb6  and     edx, 10000000h
0x180037ebc  xor     edx, eax
0x180037ebe  mov     eax, [rbx+3FCh]
0x180037ec4  mov     ecx, eax
0x180037ec6  mov     [rbx+3F8h], edx
0x180037ecc  xor     ecx, [rdi+3FCh]
0x180037ed2  and     ecx, r8d
0x180037ed5  xor     ecx, eax
0x180037ed7  mov     [rbx+3FCh], ecx
0x180037edd  mov     r8d, ecx
0x180037ee0  xor     r8d, [rdi+3FCh]
0x180037ee7  mov     eax, edx
0x180037ee9  and     r8d, r9d
0x180037eec  xor     r8d, ecx
0x180037eef  mov     [rbx+3FCh], r8d
0x180037ef6  xor     eax, [rdi+3F8h]
0x180037efc  and     eax, 20000000h
0x180037f01  xor     eax, edx
0x180037f03  mov     [rbx+3F8h], eax
0x180037f09  mov     ecx, eax
0x180037f0b  xor     ecx, [rdi+3F8h]
0x180037f11  and     ecx, 40000000h
0x180037f17  xor     ecx, eax
0x180037f19  mov     [rbx+3F8h], ecx
0x180037f1f  mov     eax, [rdi+3F8h]
0x180037f25  xor     ecx, eax
0x180037f27  btr     ecx, 1Fh
0x180037f2b  xor     ecx, eax
0x180037f2d  mov     eax, r8d
0x180037f30  mov     [rbx+3F8h], ecx
0x180037f36  xor     eax, [rdi+3FCh]
0x180037f3c  and     eax, 1
0x180037f3f  xor     eax, r8d
0x180037f42  mov     [rbx+3FCh], eax
0x180037f48  mov     ecx, eax
0x180037f4a  xor     ecx, [rdi+3FCh]
0x180037f50  and     ecx, 2
0x180037f53  xor     ecx, eax
0x180037f55  mov     [rbx+3FCh], ecx
0x180037f5b  mov     eax, ecx
0x180037f5d  xor     eax, [rdi+3FCh]
0x180037f63  and     eax, 4
0x180037f66  xor     eax, ecx
0x180037f68  mov     [rbx+3FCh], eax
0x180037f6e  mov     ecx, eax
0x180037f70  xor     ecx, [rdi+3FCh]
0x180037f76  and     ecx, 8
0x180037f79  xor     ecx, eax
0x180037f7b  mov     [rbx+3FCh], ecx
0x180037f81  mov     eax, ecx
0x180037f83  xor     eax, [rdi+3FCh]
0x180037f89  and     eax, 10h
0x180037f8c  xor     eax, ecx
  ... truncated ...
```
