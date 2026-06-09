# Js::_dynamic_initializer_for__sizeEntriesCRCs__

- ea: `0x180352400`
- end: `0x180352b8e`
- name: `Js::_dynamic_initializer_for__sizeEntriesCRCs__`
- size: `1934`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180352400`

## string_xrefs

- `0x180352765`: `recyclerLeafPageAllocator_end_committedBytes`
- `0x18035290d`: `recyclerLargeBlockPageAllocator_end_committedBytes`
- `0x180352ab5`: `recyclerWithBarrierPageAllocator_end_committedBytes`
- `0x180352551`: `threadPageAllocator_start_reservedBytes`
- `0x180352839`: `recyclerLargeBlockPageAllocator_start_committedBytes`
- `0x180352625`: `threadPageAllocator_end_reservedBytes`
- `0x18035247b`: `processCommittedBytes_start`
- `0x1803524b0`: `processCommittedBytes_end`
- `0x18035265a`: `threadPageAllocator_end_numberOfSegments`
- `0x1803524e4`: `threadPageAllocator_start_committedBytes`
- `0x18035251c`: `threadPageAllocator_start_usedBytes`
- `0x1803529e1`: `recyclerWithBarrierPageAllocator_start_committedBytes`
- `0x180352586`: `threadPageAllocator_start_numberOfSegments`
- `0x1803525f0`: `threadPageAllocator_end_usedBytes`
- `0x18035268e`: `recyclerLeafPageAllocator_start_committedBytes`
- `0x1803525bb`: `threadPageAllocator_end_committedBytes`

## pseudocode

```c
__int64 Js::_dynamic_initializer_for__sizeEntriesCRCs__()
{
  unsigned int v0; // edx
  const char *v1; // r10
  char v2; // r9
  unsigned int v3; // r8d
  char v4; // al
  const char *v5; // r10
  char v6; // al
  unsigned int v7; // r8d
  const char *v8; // r10
  char v9; // al
  unsigned int v10; // r8d
  const char *v11; // r10
  unsigned int v12; // r8d
  const char *v13; // r10
  char v14; // r9
  unsigned int v15; // r8d
  char v16; // al
  const char *v17; // r10
  char v18; // al
  unsigned int v19; // r8d
  const char *v20; // r10
  char v21; // al
  unsigned int v22; // r8d
  const char *v23; // r10
  char v24; // al
  unsigned int v25; // r8d
  const char *v26; // r10
  char v27; // al
  unsigned int v28; // r8d
  const char *v29; // r10
  char v30; // al
  unsigned int v31; // r8d
  const char *v32; // r10
  char v33; // al
  unsigned int v34; // r8d
  const char *v35; // r10
  unsigned int v36; // r8d
  const char *v37; // r10
  unsigned int v38; // r9d
  char v39; // r8
  char v40; // al
  const char *v41; // r10
  char v42; // al
  unsigned int v43; // r9d
  const char *v44; // r10
  char v45; // al
  unsigned int v46; // r9d
  const char *v47; // r10
  char v48; // al
  unsigned int v49; // r9d
  const char *v50; // r10
  char v51; // al
  unsigned int v52; // r9d
  const char *v53; // r10
  char v54; // al
  unsigned int v55; // r9d
  const char *v56; // r10
  char v57; // al
  unsigned int v58; // r9d
  const char *v59; // r10
  char v60; // al
  unsigned int v61; // r9d
  const char *v62; // r10
  char v63; // al
  unsigned int v64; // r9d
  const char *v65; // r10
  char v66; // al
  unsigned int v67; // r9d
  const char *v68; // r10
  char v69; // al
  unsigned int v70; // r9d
  const char *v71; // r10
  char v72; // al
  unsigned int v73; // r9d
  const char *v74; // r10
  char v75; // al
  unsigned int v76; // r9d
  const char *v77; // r10
  char v78; // al
  unsigned int v79; // r9d
  const char *v80; // r10
  char v81; // al
  unsigned int v82; // r9d
  const char *v83; // r10
  char v84; // al
  unsigned int v85; // r9d
  const char *v86; // r10
  char v87; // al
  unsigned int v88; // r9d
  const char *v89; // r10
  char v90; // al
  unsigned int v91; // r9d
  const char *v92; // r10
  char v93; // al
  unsigned int v94; // r9d
  const char *v95; // r10
  char v96; // al
  unsigned int v97; // r9d
  const char *v98; // r10
  char v99; // al
  unsigned int v100; // r9d
  const char *v101; // r10
  char v102; // al
  unsigned int v103; // r9d
  const char *v104; // r10
  char v105; // al
  unsigned int v106; // r9d
  const char *v107; // r9
  __int64 result; // rax

  v0 = -1;
  v1 = "processAllocaterUsedBytes_start";
  v2 = 112;
  v3 = -1;
  v4 = 112;
  do
  {
    ++v1;
    v3 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v3 ^ v4)) ^ (v3 >> 8);
    v4 = *v1;
  }
  while ( *v1 );
  v5 = "processAllocaterUsedBytes_end";
  LODWORD(Js::sizeEntriesCRCs) = ~v3;
  v6 = 112;
  v7 = -1;
  do
  {
    ++v5;
    v7 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v7 ^ v6)) ^ (v7 >> 8);
    v6 = *v5;
  }
  while ( *v5 );
  v8 = "processCommittedBytes_start";
  dword_180744364 = ~v7;
  v9 = 112;
  v10 = -1;
  do
  {
    ++v8;
    v10 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v10 ^ v9)) ^ (v10 >> 8);
    v9 = *v8;
  }
  while ( *v8 );
  v11 = "processCommittedBytes_end";
  dword_180744368 = ~v10;
  v12 = -1;
  do
  {
    ++v11;
    v12 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v12 ^ v2)) ^ (v12 >> 8);
    v2 = *v11;
  }
  while ( *v11 );
  v13 = "threadPageAllocator_start_committedBytes";
  v14 = 116;
  dword_18074436C = ~v12;
  v15 = -1;
  v16 = 116;
  do
  {
    ++v13;
    v15 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v15 ^ v16)) ^ (v15 >> 8);
    v16 = *v13;
  }
  while ( *v13 );
  v17 = "threadPageAllocator_start_usedBytes";
  dword_180744370 = ~v15;
  v18 = 116;
  v19 = -1;
  do
  {
    ++v17;
    v19 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v19 ^ v18)) ^ (v19 >> 8);
    v18 = *v17;
  }
  while ( *v17 );
  v20 = "threadPageAllocator_start_reservedBytes";
  dword_180744374 = ~v19;
  v21 = 116;
  v22 = -1;
  do
  {
    ++v20;
    v22 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v22 ^ v21)) ^ (v22 >> 8);
    v21 = *v20;
  }
  while ( *v20 );
  v23 = "threadPageAllocator_start_numberOfSegments";
  dword_180744378 = ~v22;
  v24 = 116;
  v25 = -1;
  do
  {
    ++v23;
    v25 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v25 ^ v24)) ^ (v25 >> 8);
    v24 = *v23;
  }
  while ( *v23 );
  v26 = "threadPageAllocator_end_committedBytes";
  dword_18074437C = ~v25;
  v27 = 116;
  v28 = -1;
  do
  {
    ++v26;
    v28 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v28 ^ v27)) ^ (v28 >> 8);
    v27 = *v26;
  }
  while ( *v26 );
  v29 = "threadPageAllocator_end_usedBytes";
  dword_180744380 = ~v28;
  v30 = 116;
  v31 = -1;
  do
  {
    ++v29;
    v31 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v31 ^ v30)) ^ (v31 >> 8);
    v30 = *v29;
  }
  while ( *v29 );
  v32 = "threadPageAllocator_end_reservedBytes";
  dword_180744384 = ~v31;
  v33 = 116;
  v34 = -1;
  do
  {
    ++v32;
    v34 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v34 ^ v33)) ^ (v34 >> 8);
    v33 = *v32;
  }
  while ( *v32 );
  v35 = "threadPageAllocator_end_numberOfSegments";
  dword_180744388 = ~v34;
  v36 = -1;
  do
  {
    ++v35;
    v36 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v36 ^ v14)) ^ (v36 >> 8);
    v14 = *v35;
  }
  while ( *v35 );
  v37 = "recyclerLeafPageAllocator_start_committedBytes";
  dword_18074438C = ~v36;
  v38 = -1;
  v39 = 114;
  v40 = 114;
  do
  {
    ++v37;
    v38 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v38 ^ v40)) ^ (v38 >> 8);
    v40 = *v37;
  }
  while ( *v37 );
  v41 = "recyclerLeafPageAllocator_start_usedBytes";
  dword_180744390 = ~v38;
  v42 = 114;
  v43 = -1;
  do
  {
    ++v41;
    v43 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v43 ^ v42)) ^ (v43 >> 8);
    v42 = *v41;
  }
  while ( *v41 );
  v44 = "recyclerLeafPageAllocator_start_reservedBytes";
  dword_180744394 = ~v43;
  v45 = 114;
  v46 = -1;
  do
  {
    ++v44;
    v46 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v46 ^ v45)) ^ (v46 >> 8);
    v45 = *v44;
  }
  while ( *v44 );
  v47 = "recyclerLeafPageAllocator_start_numberOfSegments";
  dword_180744398 = ~v46;
  v48 = 114;
  v49 = -1;
  do
  {
    ++v47;
    v49 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v49 ^ v48)) ^ (v49 >> 8);
    v48 = *v47;
  }
  while ( *v47 );
  v50 = "recyclerLeafPageAllocator_end_committedBytes";
  dword_18074439C = ~v49;
  v51 = 114;
  v52 = -1;
  do
  {
    ++v50;
    v52 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v52 ^ v51)) ^ (v52 >> 8);
    v51 = *v50;
  }
  while ( *v50 );
  v53 = "recyclerLeafPageAllocator_end_usedBytes";
  dword_1807443A0 = ~v52;
  v54 = 114;
  v55 = -1;
  do
  {
    ++v53;
    v55 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v55 ^ v54)) ^ (v55 >> 8);
    v54 = *v53;
  }
  while ( *v53 );
  v56 = "recyclerLeafPageAllocator_end_reservedBytes";
  dword_1807443A4 = ~v55;
  v57 = 114;
  v58 = -1;
  do
  {
    ++v56;
    v58 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v58 ^ v57)) ^ (v58 >> 8);
    v57 = *v56;
  }
  while ( *v56 );
  v59 = "recyclerLeafPageAllocator_end_numberOfSegments";
  dword_1807443A8 = ~v58;
  v60 = 114;
  v61 = -1;
  do
  {
    ++v59;
    v61 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v61 ^ v60)) ^ (v61 >> 8);
    v60 = *v59;
  }
  while ( *v59 );
  v62 = "recyclerLargeBlockPageAllocator_start_committedBytes";
  dword_1807443AC = ~v61;
  v63 = 114;
  v64 = -1;
  do
  {
    ++v62;
    v64 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v64 ^ v63)) ^ (v64 >> 8);
    v63 = *v62;
  }
  while ( *v62 );
  v65 = "recyclerLargeBlockPageAllocator_start_usedBytes";
  dword_1807443B0 = ~v64;
  v66 = 114;
  v67 = -1;
  do
  {
    ++v65;
    v67 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v67 ^ v66)) ^ (v67 >> 8);
    v66 = *v65;
  }
  while ( *v65 );
  v68 = "recyclerLargeBlockPageAllocator_start_reservedBytes";
  dword_1807443B4 = ~v67;
  v69 = 114;
  v70 = -1;
  do
  {
    ++v68;
    v70 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v70 ^ v69)) ^ (v70 >> 8);
    v69 = *v68;
  }
  while ( *v68 );
  v71 = "recyclerLargeBlockPageAllocator_start_numberOfSegments";
  dword_1807443B8 = ~v70;
  v72 = 114;
  v73 = -1;
  do
  {
    ++v71;
    v73 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v73 ^ v72)) ^ (v73 >> 8);
    v72 = *v71;
  }
  while ( *v71 );
  v74 = "recyclerLargeBlockPageAllocator_end_committedBytes";
  dword_1807443BC = ~v73;
  v75 = 114;
  v76 = -1;
  do
  {
    ++v74;
    v76 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v76 ^ v75)) ^ (v76 >> 8);
    v75 = *v74;
  }
  while ( *v74 );
  v77 = "recyclerLargeBlockPageAllocator_end_usedBytes";
  dword_1807443C0 = ~v76;
  v78 = 114;
  v79 = -1;
  do
  {
    ++v77;
    v79 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v79 ^ v78)) ^ (v79 >> 8);
    v78 = *v77;
  }
  while ( *v77 );
  v80 = "recyclerLargeBlockPageAllocator_end_reservedBytes";
  dword_1807443C4 = ~v79;
  v81 = 114;
  v82 = -1;
  do
  {
    ++v80;
    v82 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v82 ^ v81)) ^ (v82 >> 8);
    v81 = *v80;
  }
  while ( *v80 );
  v83 = "recyclerLargeBlockPageAllocator_end_numberOfSegments";
  dword_1807443C8 = ~v82;
  v84 = 114;
  v85 = -1;
  do
  {
    ++v83;
    v85 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v85 ^ v84)) ^ (v85 >> 8);
    v84 = *v83;
  }
  while ( *v83 );
  v86 = "recyclerWithBarrierPageAllocator_start_committedBytes";
  dword_1807443CC = ~v85;
  v87 = 114;
  v88 = -1;
  do
  {
    ++v86;
    v88 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v88 ^ v87)) ^ (v88 >> 8);
    v87 = *v86;
  }
  while ( *v86 );
  v89 = "recyclerWithBarrierPageAllocator_start_usedBytes";
  dword_1807443D0 = ~v88;
  v90 = 114;
  v91 = -1;
  do
  {
    ++v89;
    v91 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v91 ^ v90)) ^ (v91 >> 8);
    v90 = *v89;
  }
  while ( *v89 );
  v92 = "recyclerWithBarrierPageAllocator_start_reservedBytes";
  dword_1807443D4 = ~v91;
  v93 = 114;
  v94 = -1;
  do
  {
    ++v92;
    v94 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v94 ^ v93)) ^ (v94 >> 8);
    v93 = *v92;
  }
  while ( *v92 );
  v95 = "recyclerWithBarrierPageAllocator_start_numberOfSegments";
  dword_1807443D8 = ~v94;
  v96 = 114;
  v97 = -1;
  do
  {
    ++v95;
    v97 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v97 ^ v96)) ^ (v97 >> 8);
    v96 = *v95;
  }
  while ( *v95 );
  v98 = "recyclerWithBarrierPageAllocator_end_committedBytes";
  dword_1807443DC = ~v97;
  v99 = 114;
  v100 = -1;
  do
  {
    ++v98;
    v100 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v100 ^ v99)) ^ (v100 >> 8);
    v99 = *v98;
  }
  while ( *v98 );
  v101 = "recyclerWithBarrierPageAllocator_end_usedBytes";
  dword_1807443E0 = ~v100;
  v102 = 114;
  v103 = -1;
  do
  {
    ++v101;
    v103 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v103 ^ v102)) ^ (v103 >> 8);
    v102 = *v101;
  }
  while ( *v101 );
  v104 = "recyclerWithBarrierPageAllocator_end_reservedBytes";
  dword_1807443E4 = ~v103;
  v105 = 114;
  v106 = -1;
  do
  {
    ++v104;
    v106 = *((_DWORD *)qword_180627C80 + (unsigned __int8)(v106 ^ v105)) ^ (v106 >> 8);
    v105 = *v104;
  }
  while ( *v104 );
  dword_1807443E8 = ~v106;
  v107 = "recyclerWithBarrierPageAllocator_end_numberOfSegments";
  do
  {
    ++v107;
    result = (unsigned __int8)(v0 ^ v39);
    v0 = *((_DWORD *)qword_180627C80 + result) ^ (v0 >> 8);
    v39 = *v107;
  }
  while ( *v107 );
  dword_1807443EC = ~v0;
  return result;
}

```

## disassembly

```asm
0x180352400  mov     [rsp+arg_0], rbx
0x180352405  or      edx, 0FFFFFFFFh
0x180352408  lea     r10, aProcessallocat; "processAllocaterUsedBytes_start"
0x18035240f  mov     r9b, 70h ; 'p'
0x180352412  lea     rbx, qword_180627C80
0x180352419  mov     r8d, edx
0x18035241c  mov     al, r9b
0x18035241f  mov     r11d, 1
0x180352425  movsx   ecx, al
0x180352428  add     r10, r11
0x18035242b  mov     eax, r8d
0x18035242e  shr     r8d, 8
0x180352432  xor     rcx, rax
0x180352435  movzx   eax, cl
0x180352438  xor     r8d, [rbx+rax*4]
0x18035243c  mov     al, [r10]
0x18035243f  test    al, al
0x180352441  jnz     short loc_180352425
0x180352443  not     r8d
0x180352446  lea     r10, aProcessallocat_0; "processAllocaterUsedBytes_end"
0x18035244d  mov     cs:?sizeEntriesCRCs@Js@@3PAIA, r8d; uint near * Js::sizeEntriesCRCs
0x180352454  mov     al, r9b
0x180352457  mov     r8d, edx
0x18035245a  movsx   ecx, al
0x18035245d  add     r10, r11
0x180352460  mov     eax, r8d
0x180352463  shr     r8d, 8
0x180352467  xor     rcx, rax
0x18035246a  movzx   eax, cl
0x18035246d  xor     r8d, [rbx+rax*4]
0x180352471  mov     al, [r10]
0x180352474  test    al, al
0x180352476  jnz     short loc_18035245A
0x180352478  not     r8d
0x18035247b  lea     r10, aProcesscommitt_0; "processCommittedBytes_start"
0x180352482  mov     cs:dword_180744364, r8d
0x180352489  mov     al, r9b
0x18035248c  mov     r8d, edx
0x18035248f  movsx   ecx, al
0x180352492  add     r10, r11
0x180352495  mov     eax, r8d
0x180352498  shr     r8d, 8
0x18035249c  xor     rcx, rax
0x18035249f  movzx   eax, cl
0x1803524a2  xor     r8d, [rbx+rax*4]
0x1803524a6  mov     al, [r10]
0x1803524a9  test    al, al
0x1803524ab  jnz     short loc_18035248F
0x1803524ad  not     r8d
0x1803524b0  lea     r10, aProcesscommitt; "processCommittedBytes_end"
0x1803524b7  mov     cs:dword_180744368, r8d
0x1803524be  mov     r8d, edx
0x1803524c1  mov     eax, r8d
0x1803524c4  movsx   ecx, r9b
0x1803524c8  xor     rcx, rax
0x1803524cb  shr     r8d, 8
0x1803524cf  add     r10, r11
0x1803524d2  movzx   eax, cl
0x1803524d5  xor     r8d, [rbx+rax*4]
0x1803524d9  mov     r9b, [r10]
0x1803524dc  test    r9b, r9b
0x1803524df  jnz     short loc_1803524C1
0x1803524e1  not     r8d
0x1803524e4  lea     r10, aThreadpageallo_4; "threadPageAllocator_start_committedByte"...
0x1803524eb  mov     r9b, 74h ; 't'
0x1803524ee  mov     cs:dword_18074436C, r8d
0x1803524f5  mov     r8d, edx
0x1803524f8  mov     al, r9b
0x1803524fb  movsx   ecx, al
0x1803524fe  add     r10, r11
0x180352501  mov     eax, r8d
0x180352504  shr     r8d, 8
0x180352508  xor     rcx, rax
0x18035250b  movzx   eax, cl
0x18035250e  xor     r8d, [rbx+rax*4]
0x180352512  mov     al, [r10]
0x180352515  test    al, al
0x180352517  jnz     short loc_1803524FB
0x180352519  not     r8d
0x18035251c  lea     r10, aThreadpageallo_2; "threadPageAllocator_start_usedBytes"
0x180352523  mov     cs:dword_180744370, r8d
0x18035252a  mov     al, r9b
0x18035252d  mov     r8d, edx
0x180352530  movsx   ecx, al
0x180352533  add     r10, r11
0x180352536  mov     eax, r8d
0x180352539  shr     r8d, 8
0x18035253d  xor     rcx, rax
0x180352540  movzx   eax, cl
0x180352543  xor     r8d, [rbx+rax*4]
0x180352547  mov     al, [r10]
0x18035254a  test    al, al
0x18035254c  jnz     short loc_180352530
0x18035254e  not     r8d
0x180352551  lea     r10, aThreadpageallo_5; "threadPageAllocator_start_reservedBytes"
0x180352558  mov     cs:dword_180744374, r8d
0x18035255f  mov     al, r9b
0x180352562  mov     r8d, edx
0x180352565  movsx   ecx, al
0x180352568  add     r10, r11
0x18035256b  mov     eax, r8d
0x18035256e  shr     r8d, 8
0x180352572  xor     rcx, rax
0x180352575  movzx   eax, cl
0x180352578  xor     r8d, [rbx+rax*4]
0x18035257c  mov     al, [r10]
0x18035257f  test    al, al
0x180352581  jnz     short loc_180352565
0x180352583  not     r8d
0x180352586  lea     r10, aThreadpageallo; "threadPageAllocator_start_numberOfSegme"...
0x18035258d  mov     cs:dword_180744378, r8d
0x180352594  mov     al, r9b
0x180352597  mov     r8d, edx
0x18035259a  movsx   ecx, al
0x18035259d  add     r10, r11
0x1803525a0  mov     eax, r8d
0x1803525a3  shr     r8d, 8
0x1803525a7  xor     rcx, rax
0x1803525aa  movzx   eax, cl
0x1803525ad  xor     r8d, [rbx+rax*4]
0x1803525b1  mov     al, [r10]
0x1803525b4  test    al, al
0x1803525b6  jnz     short loc_18035259A
0x1803525b8  not     r8d
0x1803525bb  lea     r10, aThreadpageallo_0; "threadPageAllocator_end_committedBytes"
0x1803525c2  mov     cs:dword_18074437C, r8d
0x1803525c9  mov     al, r9b
0x1803525cc  mov     r8d, edx
0x1803525cf  movsx   ecx, al
0x1803525d2  add     r10, r11
0x1803525d5  mov     eax, r8d
0x1803525d8  shr     r8d, 8
0x1803525dc  xor     rcx, rax
0x1803525df  movzx   eax, cl
0x1803525e2  xor     r8d, [rbx+rax*4]
0x1803525e6  mov     al, [r10]
0x1803525e9  test    al, al
0x1803525eb  jnz     short loc_1803525CF
0x1803525ed  not     r8d
0x1803525f0  lea     r10, aThreadpageallo_6; "threadPageAllocator_end_usedBytes"
0x1803525f7  mov     cs:dword_180744380, r8d
0x1803525fe  mov     al, r9b
0x180352601  mov     r8d, edx
0x180352604  movsx   ecx, al
0x180352607  add     r10, r11
0x18035260a  mov     eax, r8d
0x18035260d  shr     r8d, 8
0x180352611  xor     rcx, rax
0x180352614  movzx   eax, cl
0x180352617  xor     r8d, [rbx+rax*4]
0x18035261b  mov     al, [r10]
0x18035261e  test    al, al
0x180352620  jnz     short loc_180352604
0x180352622  not     r8d
0x180352625  lea     r10, aThreadpageallo_1; "threadPageAllocator_end_reservedBytes"
0x18035262c  mov     cs:dword_180744384, r8d
0x180352633  mov     al, r9b
0x180352636  mov     r8d, edx
0x180352639  movsx   ecx, al
0x18035263c  add     r10, r11
0x18035263f  mov     eax, r8d
0x180352642  shr     r8d, 8
0x180352646  xor     rcx, rax
0x180352649  movzx   eax, cl
0x18035264c  xor     r8d, [rbx+rax*4]
0x180352650  mov     al, [r10]
0x180352653  test    al, al
0x180352655  jnz     short loc_180352639
0x180352657  not     r8d
0x18035265a  lea     r10, aThreadpageallo_3; "threadPageAllocator_end_numberOfSegment"...
0x180352661  mov     cs:dword_180744388, r8d
0x180352668  mov     r8d, edx
0x18035266b  mov     eax, r8d
0x18035266e  movsx   ecx, r9b
0x180352672  xor     rcx, rax
0x180352675  shr     r8d, 8
0x180352679  add     r10, r11
0x18035267c  movzx   eax, cl
0x18035267f  xor     r8d, [rbx+rax*4]
0x180352683  mov     r9b, [r10]
0x180352686  test    r9b, r9b
0x180352689  jnz     short loc_18035266B
0x18035268b  not     r8d
0x18035268e  lea     r10, aRecyclerleafpa_3; "recyclerLeafPageAllocator_start_committ"...
0x180352695  mov     cs:dword_18074438C, r8d
0x18035269c  mov     r9d, edx
0x18035269f  mov     r8b, 72h ; 'r'
0x1803526a2  mov     al, r8b
0x1803526a5  movsx   ecx, al
0x1803526a8  add     r10, r11
0x1803526ab  mov     eax, r9d
0x1803526ae  shr     r9d, 8
0x1803526b2  xor     rcx, rax
0x1803526b5  movzx   eax, cl
0x1803526b8  xor     r9d, [rbx+rax*4]
0x1803526bc  mov     al, [r10]
0x1803526bf  test    al, al
0x1803526c1  jnz     short loc_1803526A5
0x1803526c3  not     r9d
0x1803526c6  lea     r10, aRecyclerleafpa_4; "recyclerLeafPageAllocator_start_usedByt"...
0x1803526cd  mov     cs:dword_180744390, r9d
0x1803526d4  mov     al, r8b
0x1803526d7  mov     r9d, edx
0x1803526da  movsx   ecx, al
0x1803526dd  add     r10, r11
0x1803526e0  mov     eax, r9d
0x1803526e3  shr     r9d, 8
0x1803526e7  xor     rcx, rax
0x1803526ea  movzx   eax, cl
0x1803526ed  xor     r9d, [rbx+rax*4]
0x1803526f1  mov     al, [r10]
0x1803526f4  test    al, al
0x1803526f6  jnz     short loc_1803526DA
0x1803526f8  not     r9d
0x1803526fb  lea     r10, aRecyclerleafpa_2; "recyclerLeafPageAllocator_start_reserve"...
0x180352702  mov     cs:dword_180744394, r9d
0x180352709  mov     al, r8b
0x18035270c  mov     r9d, edx
0x18035270f  movsx   ecx, al
0x180352712  add     r10, r11
0x180352715  mov     eax, r9d
0x180352718  shr     r9d, 8
0x18035271c  xor     rcx, rax
0x18035271f  movzx   eax, cl
0x180352722  xor     r9d, [rbx+rax*4]
0x180352726  mov     al, [r10]
0x180352729  test    al, al
0x18035272b  jnz     short loc_18035270F
0x18035272d  not     r9d
0x180352730  lea     r10, aRecyclerleafpa_1; "recyclerLeafPageAllocator_start_numberO"...
0x180352737  mov     cs:dword_180744398, r9d
0x18035273e  mov     al, r8b
0x180352741  mov     r9d, edx
0x180352744  movsx   ecx, al
0x180352747  add     r10, r11
0x18035274a  mov     eax, r9d
0x18035274d  shr     r9d, 8
0x180352751  xor     rcx, rax
0x180352754  movzx   eax, cl
0x180352757  xor     r9d, [rbx+rax*4]
0x18035275b  mov     al, [r10]
0x18035275e  test    al, al
0x180352760  jnz     short loc_180352744
0x180352762  not     r9d
0x180352765  lea     r10, aRecyclerleafpa; "recyclerLeafPageAllocator_end_committed"...
0x18035276c  mov     cs:dword_18074439C, r9d
0x180352773  mov     al, r8b
0x180352776  mov     r9d, edx
0x180352779  movsx   ecx, al
0x18035277c  add     r10, r11
0x18035277f  mov     eax, r9d
0x180352782  shr     r9d, 8
0x180352786  xor     rcx, rax
0x180352789  movzx   eax, cl
0x18035278c  xor     r9d, [rbx+rax*4]
0x180352790  mov     al, [r10]
0x180352793  test    al, al
0x180352795  jnz     short loc_180352779
0x180352797  not     r9d
0x18035279a  lea     r10, aRecyclerleafpa_0; "recyclerLeafPageAllocator_end_usedBytes"
0x1803527a1  mov     cs:dword_1807443A0, r9d
0x1803527a8  mov     al, r8b
0x1803527ab  mov     r9d, edx
0x1803527ae  movsx   ecx, al
0x1803527b1  add     r10, r11
0x1803527b4  mov     eax, r9d
0x1803527b7  shr     r9d, 8
0x1803527bb  xor     rcx, rax
0x1803527be  movzx   eax, cl
0x1803527c1  xor     r9d, [rbx+rax*4]
0x1803527c5  mov     al, [r10]
0x1803527c8  test    al, al
0x1803527ca  jnz     short loc_1803527AE
0x1803527cc  not     r9d
0x1803527cf  lea     r10, aRecyclerleafpa_5; "recyclerLeafPageAllocator_end_reservedB"...
0x1803527d6  mov     cs:dword_1807443A4, r9d
0x1803527dd  mov     al, r8b
0x1803527e0  mov     r9d, edx
0x1803527e3  movsx   ecx, al
0x1803527e6  add     r10, r11
0x1803527e9  mov     eax, r9d
0x1803527ec  shr     r9d, 8
0x1803527f0  xor     rcx, rax
0x1803527f3  movzx   eax, cl
0x1803527f6  xor     r9d, [rbx+rax*4]
0x1803527fa  mov     al, [r10]
0x1803527fd  test    al, al
0x1803527ff  jnz     short loc_1803527E3
0x180352801  not     r9d
0x180352804  lea     r10, aRecyclerleafpa_6; "recyclerLeafPageAllocator_end_numberOfS"...
0x18035280b  mov     cs:dword_1807443A8, r9d
0x180352812  mov     al, r8b
0x180352815  mov     r9d, edx
0x180352818  movsx   ecx, al
0x18035281b  add     r10, r11
0x18035281e  mov     eax, r9d
0x180352821  shr     r9d, 8
0x180352825  xor     rcx, rax
0x180352828  movzx   eax, cl
0x18035282b  xor     r9d, [rbx+rax*4]
  ... truncated ...
```
