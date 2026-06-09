# PsmpUpdateApplicationCountersForJob

- ea: `0x180012cf0`
- end: `0x1800133db`
- name: `PsmpUpdateApplicationCountersForJob`
- size: `1771`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180003504`

## callees

- `0x180012cf0`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtQueryInformationJobObject` at `0x180012d85`
- `ntdll!NtQueryInformationJobObject` at `0x180012d85`

## pseudocode

```c
__int64 __fastcall PsmpUpdateApplicationCountersForJob(__int64 a1, int a2)
{
  void *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v8; // rbx
  _BYTE JobInformation[96]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+90h] [rbp-70h]
  __int64 v11; // [rsp+98h] [rbp-68h]
  __int64 v12; // [rsp+A0h] [rbp-60h]
  __int64 v13; // [rsp+A8h] [rbp-58h]
  __int64 v14; // [rsp+B0h] [rbp-50h]
  __int64 v15; // [rsp+B8h] [rbp-48h]
  __int64 v16; // [rsp+D0h] [rbp-30h]
  __int64 v17; // [rsp+D8h] [rbp-28h]
  __int64 v18; // [rsp+E0h] [rbp-20h]
  __int64 v19; // [rsp+E8h] [rbp-18h]
  __int64 v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]
  __int64 v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  __int64 v24; // [rsp+110h] [rbp+10h]
  __int64 v25; // [rsp+118h] [rbp+18h]
  __int64 v26; // [rsp+120h] [rbp+20h]
  __int64 v27; // [rsp+128h] [rbp+28h]
  __int64 v28; // [rsp+130h] [rbp+30h]
  __int64 v29; // [rsp+160h] [rbp+60h]
  __int64 v30; // [rsp+168h] [rbp+68h]
  __int64 v31; // [rsp+170h] [rbp+70h]
  __int64 v32; // [rsp+178h] [rbp+78h]
  __int64 v33; // [rsp+180h] [rbp+80h]
  __int64 v34; // [rsp+188h] [rbp+88h]
  __int64 v35; // [rsp+190h] [rbp+90h]
  __int64 v36; // [rsp+198h] [rbp+98h]
  __int64 v37; // [rsp+1A0h] [rbp+A0h]
  __int64 v38; // [rsp+1A8h] [rbp+A8h]
  __int64 v39; // [rsp+1B0h] [rbp+B0h]
  __int64 v40; // [rsp+1B8h] [rbp+B8h]
  __int64 v41; // [rsp+1C0h] [rbp+C0h]
  __int64 v42; // [rsp+1C8h] [rbp+C8h]
  __int64 v43; // [rsp+1D0h] [rbp+D0h]
  __int64 v44; // [rsp+1D8h] [rbp+D8h]

  memset_0(JobInformation, 0, 0x1B0u);
  if ( a2 == 6 )
  {
    v4 = *(void **)(a1 + 184);
    v5 = 704;
    v6 = 352;
  }
  else
  {
    if ( a2 != 8 )
      return 3221225485LL;
    v4 = *(void **)(a1 + 200);
    v5 = 3872;
    v6 = 3520;
  }
  if ( v4 )
  {
    v8 = v5 + a1;
    NtQueryInformationJobObject(v4, JobObjectBasicProcessIdList|0x10, JobInformation, 0x1B0u, 0);
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 24) += v15 - *(_QWORD *)(v6 + a1 + 24);
    *(_QWORD *)(v6 + a1 + 24) = v15;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 56) += v12 - *(_QWORD *)(v6 + a1 + 56);
    *(_QWORD *)(v6 + a1 + 56) = v12;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 64) += v13 - *(_QWORD *)(v6 + a1 + 64);
    *(_QWORD *)(v6 + a1 + 64) = v13;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 72) += v14 - *(_QWORD *)(v6 + a1 + 72);
    *(_QWORD *)(v6 + a1 + 72) = v14;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 40) += v10 - *(_QWORD *)(v6 + a1 + 40);
    *(_QWORD *)(v6 + a1 + 40) = v10;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 48) += v11 - *(_QWORD *)(v6 + a1 + 48);
    *(_QWORD *)(v6 + a1 + 48) = v11;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 144) += v24 - *(_QWORD *)(v6 + a1 + 144);
    *(_QWORD *)(v6 + a1 + 144) = v24;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 152) += v25 - *(_QWORD *)(v6 + a1 + 152);
    *(_QWORD *)(v6 + a1 + 152) = v25;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 160) += v26 - *(_QWORD *)(v6 + a1 + 160);
    *(_QWORD *)(v6 + a1 + 160) = v26;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 168) += v27 - *(_QWORD *)(v6 + a1 + 168);
    *(_QWORD *)(v6 + a1 + 168) = v27;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 176) += v28 - *(_QWORD *)(v6 + a1 + 176);
    *(_QWORD *)(v6 + a1 + 176) = v28;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 80) += v16 - *(_QWORD *)(v6 + a1 + 80);
    *(_QWORD *)(v6 + a1 + 80) = v16;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 288) += v37 - *(_QWORD *)(v6 + a1 + 288);
    *(_QWORD *)(v6 + a1 + 288) = v37;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 224) += v29 - *(_QWORD *)(v6 + a1 + 224);
    *(_QWORD *)(v6 + a1 + 224) = v29;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 88) += v17 - *(_QWORD *)(v6 + a1 + 88);
    *(_QWORD *)(v6 + a1 + 88) = v17;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 296) += v38 - *(_QWORD *)(v6 + a1 + 296);
    *(_QWORD *)(v6 + a1 + 296) = v38;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 232) += v30 - *(_QWORD *)(v6 + a1 + 232);
    *(_QWORD *)(v6 + a1 + 232) = v30;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 96) += v18 - *(_QWORD *)(v6 + a1 + 96);
    *(_QWORD *)(v6 + a1 + 96) = v18;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 304) += v39 - *(_QWORD *)(v6 + a1 + 304);
    *(_QWORD *)(v6 + a1 + 304) = v39;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 240) += v31 - *(_QWORD *)(v6 + a1 + 240);
    *(_QWORD *)(v6 + a1 + 240) = v31;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 104) += v19 - *(_QWORD *)(v6 + a1 + 104);
    *(_QWORD *)(v6 + a1 + 104) = v19;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 312) += v40 - *(_QWORD *)(v6 + a1 + 312);
    *(_QWORD *)(v6 + a1 + 312) = v40;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 248) += v32 - *(_QWORD *)(v6 + a1 + 248);
    *(_QWORD *)(v6 + a1 + 248) = v32;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 112) += v20 - *(_QWORD *)(v6 + a1 + 112);
    *(_QWORD *)(v6 + a1 + 112) = v20;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 320) += v41 - *(_QWORD *)(v6 + a1 + 320);
    *(_QWORD *)(v6 + a1 + 320) = v41;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 256) += v33 - *(_QWORD *)(v6 + a1 + 256);
    *(_QWORD *)(v6 + a1 + 256) = v33;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 120) += v21 - *(_QWORD *)(v6 + a1 + 120);
    *(_QWORD *)(v6 + a1 + 120) = v21;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 328) += v42 - *(_QWORD *)(v6 + a1 + 328);
    *(_QWORD *)(v6 + a1 + 328) = v42;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 264) += v34 - *(_QWORD *)(v6 + a1 + 264);
    *(_QWORD *)(v6 + a1 + 264) = v34;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 128) += v22 - *(_QWORD *)(v6 + a1 + 128);
    *(_QWORD *)(v6 + a1 + 128) = v22;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 336) += v43 - *(_QWORD *)(v6 + a1 + 336);
    *(_QWORD *)(v6 + a1 + 336) = v43;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 272) += v35 - *(_QWORD *)(v6 + a1 + 272);
    *(_QWORD *)(v6 + a1 + 272) = v35;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 136) += v23 - *(_QWORD *)(v6 + a1 + 136);
    *(_QWORD *)(v6 + a1 + 136) = v23;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 344) += v44 - *(_QWORD *)(v6 + a1 + 344);
    *(_QWORD *)(v6 + a1 + 344) = v44;
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + v8 + 280) += v36 - *(_QWORD *)(v6 + a1 + 280);
    *(_QWORD *)(v6 + a1 + 280) = v36;
  }
  return 0;
}

```

## disassembly

```asm
0x180012cf0  push    rbp
0x180012cf2  push    rbx
0x180012cf3  push    rsi
0x180012cf4  push    rdi
0x180012cf5  lea     rbp, [rsp-0F8h]
0x180012cfd  sub     rsp, 1F8h
0x180012d04  mov     rax, cs:__security_cookie
0x180012d0b  xor     rax, rsp
0x180012d0e  mov     [rbp+110h+var_30], rax
0x180012d15  mov     ebx, edx
0x180012d17  mov     rdi, rcx
0x180012d1a  xor     edx, edx; Val
0x180012d1c  lea     rcx, [rsp+210h+JobInformation]; void *
0x180012d21  mov     r8d, 1B0h; Size
0x180012d27  call    memset_0
0x180012d2c  cmp     ebx, 6
0x180012d2f  jnz     loc_1800133B6
0x180012d35  mov     rcx, [rdi+0B8h]; JobHandle
0x180012d3c  mov     eax, 2C0h
0x180012d41  mov     esi, 160h
0x180012d46  test    rcx, rcx
0x180012d49  jnz     short loc_180012D68
0x180012d4b  xor     eax, eax
0x180012d4d  mov     rcx, [rbp+110h+var_30]
0x180012d54  xor     rcx, rsp; StackCookie
0x180012d57  call    __security_check_cookie
0x180012d5c  add     rsp, 1F8h
0x180012d63  pop     rdi
0x180012d64  pop     rsi
0x180012d65  pop     rbx
0x180012d66  pop     rbp
0x180012d67  retn
0x180012d68  mov     r9d, 1B0h; JobInformationLength
0x180012d6e  mov     [rsp+210h+ReturnLength], 0; ReturnLength
0x180012d77  lea     r8, [rsp+210h+JobInformation]; JobInformation
0x180012d7c  mov     edx, 13h; JobInformationClass
0x180012d81  lea     rbx, [rax+rdi]
0x180012d85  call    cs:__imp_NtQueryInformationJobObject
0x180012d8b  movsxd  rax, dword ptr [rdi+158h]
0x180012d92  imul    rcx, rax, 160h
0x180012d99  mov     rax, [rbp+110h+var_158]
0x180012d9d  sub     rax, [rsi+rdi+18h]
0x180012da2  add     [rcx+rbx+18h], rax
0x180012da7  mov     rax, [rbp+110h+var_158]
0x180012dab  mov     [rsi+rdi+18h], rax
0x180012db0  movsxd  rax, dword ptr [rdi+158h]
0x180012db7  imul    rcx, rax, 160h
0x180012dbe  mov     rax, [rbp+110h+var_170]
0x180012dc2  sub     rax, [rsi+rdi+38h]
0x180012dc7  add     [rcx+rbx+38h], rax
0x180012dcc  mov     rax, [rbp+110h+var_170]
0x180012dd0  mov     [rsi+rdi+38h], rax
0x180012dd5  movsxd  rax, dword ptr [rdi+158h]
0x180012ddc  imul    rcx, rax, 160h
0x180012de3  mov     rax, [rbp+110h+var_168]
0x180012de7  sub     rax, [rsi+rdi+40h]
0x180012dec  add     [rcx+rbx+40h], rax
0x180012df1  mov     rax, [rbp+110h+var_168]
0x180012df5  mov     [rsi+rdi+40h], rax
0x180012dfa  movsxd  rax, dword ptr [rdi+158h]
0x180012e01  imul    rcx, rax, 160h
0x180012e08  mov     rax, [rbp+110h+var_160]
0x180012e0c  sub     rax, [rsi+rdi+48h]
0x180012e11  add     [rcx+rbx+48h], rax
0x180012e16  mov     rax, [rbp+110h+var_160]
0x180012e1a  mov     [rsi+rdi+48h], rax
0x180012e1f  movsxd  rax, dword ptr [rdi+158h]
0x180012e26  imul    rcx, rax, 160h
0x180012e2d  mov     rax, [rbp+110h+var_180]
0x180012e31  sub     rax, [rsi+rdi+28h]
0x180012e36  add     [rcx+rbx+28h], rax
0x180012e3b  mov     rax, [rbp+110h+var_180]
0x180012e3f  mov     [rsi+rdi+28h], rax
0x180012e44  movsxd  rax, dword ptr [rdi+158h]
0x180012e4b  imul    rcx, rax, 160h
0x180012e52  mov     rax, [rbp+110h+var_178]
0x180012e56  sub     rax, [rsi+rdi+30h]
0x180012e5b  add     [rcx+rbx+30h], rax
0x180012e60  mov     rax, [rbp+110h+var_178]
0x180012e64  mov     [rsi+rdi+30h], rax
0x180012e69  movsxd  rax, dword ptr [rdi+158h]
0x180012e70  imul    rcx, rax, 160h
0x180012e77  mov     rax, [rbp+110h+var_100]
0x180012e7b  sub     rax, [rsi+rdi+90h]
0x180012e83  add     [rcx+rbx+90h], rax
0x180012e8b  mov     rax, [rbp+110h+var_100]
0x180012e8f  mov     [rsi+rdi+90h], rax
0x180012e97  movsxd  rax, dword ptr [rdi+158h]
0x180012e9e  imul    rcx, rax, 160h
0x180012ea5  mov     rax, [rbp+110h+var_F8]
0x180012ea9  sub     rax, [rsi+rdi+98h]
0x180012eb1  add     [rcx+rbx+98h], rax
0x180012eb9  mov     rax, [rbp+110h+var_F8]
0x180012ebd  mov     [rsi+rdi+98h], rax
0x180012ec5  movsxd  rax, dword ptr [rdi+158h]
0x180012ecc  imul    rcx, rax, 160h
0x180012ed3  mov     rax, [rbp+110h+var_F0]
0x180012ed7  sub     rax, [rsi+rdi+0A0h]
0x180012edf  add     [rcx+rbx+0A0h], rax
0x180012ee7  mov     rax, [rbp+110h+var_F0]
0x180012eeb  mov     [rsi+rdi+0A0h], rax
0x180012ef3  movsxd  rax, dword ptr [rdi+158h]
0x180012efa  imul    rcx, rax, 160h
0x180012f01  mov     rax, [rbp+110h+var_E8]
0x180012f05  sub     rax, [rsi+rdi+0A8h]
0x180012f0d  add     [rcx+rbx+0A8h], rax
0x180012f15  mov     rax, [rbp+110h+var_E8]
0x180012f19  mov     [rsi+rdi+0A8h], rax
0x180012f21  movsxd  rax, dword ptr [rdi+158h]
0x180012f28  imul    rcx, rax, 160h
0x180012f2f  mov     rax, [rbp+110h+var_E0]
0x180012f33  sub     rax, [rsi+rdi+0B0h]
0x180012f3b  add     [rcx+rbx+0B0h], rax
0x180012f43  mov     rax, [rbp+110h+var_E0]
0x180012f47  mov     [rsi+rdi+0B0h], rax
0x180012f4f  movsxd  rax, dword ptr [rdi+158h]
0x180012f56  imul    rcx, rax, 160h
0x180012f5d  mov     rax, [rbp+110h+var_140]
0x180012f61  sub     rax, [rsi+rdi+50h]
0x180012f66  add     [rcx+rbx+50h], rax
0x180012f6b  mov     rax, [rbp+110h+var_140]
0x180012f6f  mov     [rsi+rdi+50h], rax
0x180012f74  movsxd  rax, dword ptr [rdi+158h]
0x180012f7b  imul    rcx, rax, 160h
0x180012f82  mov     rax, [rbp+110h+var_70]
0x180012f89  sub     rax, [rsi+rdi+120h]
0x180012f91  add     [rcx+rbx+120h], rax
0x180012f99  mov     rax, [rbp+110h+var_70]
0x180012fa0  mov     [rsi+rdi+120h], rax
0x180012fa8  movsxd  rax, dword ptr [rdi+158h]
0x180012faf  imul    rcx, rax, 160h
0x180012fb6  mov     rax, [rbp+110h+var_B0]
0x180012fba  sub     rax, [rsi+rdi+0E0h]
0x180012fc2  add     [rcx+rbx+0E0h], rax
0x180012fca  mov     rax, [rbp+110h+var_B0]
0x180012fce  mov     [rsi+rdi+0E0h], rax
0x180012fd6  movsxd  rax, dword ptr [rdi+158h]
0x180012fdd  imul    rcx, rax, 160h
0x180012fe4  mov     rax, [rbp+110h+var_138]
0x180012fe8  sub     rax, [rsi+rdi+58h]
0x180012fed  add     [rcx+rbx+58h], rax
0x180012ff2  mov     rax, [rbp+110h+var_138]
0x180012ff6  mov     [rsi+rdi+58h], rax
0x180012ffb  movsxd  rax, dword ptr [rdi+158h]
0x180013002  imul    rcx, rax, 160h
0x180013009  mov     rax, [rbp+110h+var_68]
0x180013010  sub     rax, [rsi+rdi+128h]
0x180013018  add     [rcx+rbx+128h], rax
0x180013020  mov     rax, [rbp+110h+var_68]
0x180013027  mov     [rsi+rdi+128h], rax
0x18001302f  movsxd  rax, dword ptr [rdi+158h]
0x180013036  imul    rcx, rax, 160h
0x18001303d  mov     rax, [rbp+110h+var_A8]
0x180013041  sub     rax, [rsi+rdi+0E8h]
0x180013049  add     [rcx+rbx+0E8h], rax
0x180013051  mov     rax, [rbp+110h+var_A8]
0x180013055  mov     [rsi+rdi+0E8h], rax
0x18001305d  movsxd  rax, dword ptr [rdi+158h]
0x180013064  imul    rcx, rax, 160h
0x18001306b  mov     rax, [rbp+110h+var_130]
0x18001306f  sub     rax, [rsi+rdi+60h]
0x180013074  add     [rcx+rbx+60h], rax
0x180013079  mov     rax, [rbp+110h+var_130]
0x18001307d  mov     [rsi+rdi+60h], rax
0x180013082  movsxd  rax, dword ptr [rdi+158h]
0x180013089  imul    rcx, rax, 160h
0x180013090  mov     rax, [rbp+110h+var_60]
0x180013097  sub     rax, [rsi+rdi+130h]
0x18001309f  add     [rcx+rbx+130h], rax
0x1800130a7  mov     rax, [rbp+110h+var_60]
0x1800130ae  mov     [rsi+rdi+130h], rax
0x1800130b6  movsxd  rax, dword ptr [rdi+158h]
0x1800130bd  imul    rcx, rax, 160h
0x1800130c4  mov     rax, [rbp+110h+var_A0]
0x1800130c8  sub     rax, [rsi+rdi+0F0h]
0x1800130d0  add     [rcx+rbx+0F0h], rax
0x1800130d8  mov     rax, [rbp+110h+var_A0]
0x1800130dc  mov     [rsi+rdi+0F0h], rax
0x1800130e4  movsxd  rax, dword ptr [rdi+158h]
0x1800130eb  imul    rcx, rax, 160h
0x1800130f2  mov     rax, [rbp+110h+var_128]
0x1800130f6  sub     rax, [rsi+rdi+68h]
0x1800130fb  add     [rcx+rbx+68h], rax
0x180013100  mov     rax, [rbp+110h+var_128]
0x180013104  mov     [rsi+rdi+68h], rax
0x180013109  movsxd  rax, dword ptr [rdi+158h]
0x180013110  imul    rcx, rax, 160h
0x180013117  mov     rax, [rbp+110h+var_58]
0x18001311e  sub     rax, [rsi+rdi+138h]
0x180013126  add     [rcx+rbx+138h], rax
0x18001312e  mov     rax, [rbp+110h+var_58]
0x180013135  mov     [rsi+rdi+138h], rax
0x18001313d  movsxd  rax, dword ptr [rdi+158h]
0x180013144  imul    rcx, rax, 160h
0x18001314b  mov     rax, [rbp+110h+var_98]
0x18001314f  sub     rax, [rsi+rdi+0F8h]
0x180013157  add     [rcx+rbx+0F8h], rax
0x18001315f  mov     rax, [rbp+110h+var_98]
0x180013163  mov     [rsi+rdi+0F8h], rax
0x18001316b  movsxd  rax, dword ptr [rdi+158h]
0x180013172  imul    rcx, rax, 160h
0x180013179  mov     rax, [rbp+110h+var_120]
0x18001317d  sub     rax, [rsi+rdi+70h]
0x180013182  add     [rcx+rbx+70h], rax
0x180013187  mov     rax, [rbp+110h+var_120]
0x18001318b  mov     [rsi+rdi+70h], rax
0x180013190  movsxd  rax, dword ptr [rdi+158h]
0x180013197  imul    rcx, rax, 160h
0x18001319e  mov     rax, [rbp+110h+var_50]
0x1800131a5  sub     rax, [rsi+rdi+140h]
0x1800131ad  add     [rcx+rbx+140h], rax
0x1800131b5  mov     rax, [rbp+110h+var_50]
0x1800131bc  mov     [rsi+rdi+140h], rax
0x1800131c4  movsxd  rax, dword ptr [rdi+158h]
0x1800131cb  imul    rcx, rax, 160h
0x1800131d2  mov     rax, [rbp+110h+var_90]
0x1800131d9  sub     rax, [rsi+rdi+100h]
0x1800131e1  add     [rcx+rbx+100h], rax
0x1800131e9  mov     rax, [rbp+110h+var_90]
0x1800131f0  mov     [rsi+rdi+100h], rax
0x1800131f8  movsxd  rax, dword ptr [rdi+158h]
0x1800131ff  imul    rcx, rax, 160h
0x180013206  mov     rax, [rbp+110h+var_118]
0x18001320a  sub     rax, [rsi+rdi+78h]
0x18001320f  add     [rcx+rbx+78h], rax
0x180013214  mov     rax, [rbp+110h+var_118]
0x180013218  mov     [rsi+rdi+78h], rax
0x18001321d  movsxd  rax, dword ptr [rdi+158h]
0x180013224  imul    rcx, rax, 160h
0x18001322b  mov     rax, [rbp+110h+var_48]
0x180013232  sub     rax, [rsi+rdi+148h]
0x18001323a  add     [rcx+rbx+148h], rax
0x180013242  mov     rax, [rbp+110h+var_48]
0x180013249  mov     [rsi+rdi+148h], rax
0x180013251  movsxd  rax, dword ptr [rdi+158h]
0x180013258  imul    rcx, rax, 160h
0x18001325f  mov     rax, [rbp+110h+var_88]
0x180013266  sub     rax, [rsi+rdi+108h]
0x18001326e  add     [rcx+rbx+108h], rax
0x180013276  mov     rax, [rbp+110h+var_88]
0x18001327d  mov     [rsi+rdi+108h], rax
0x180013285  movsxd  rax, dword ptr [rdi+158h]
0x18001328c  imul    rcx, rax, 160h
0x180013293  mov     rax, [rbp+110h+var_110]
0x180013297  sub     rax, [rsi+rdi+80h]
0x18001329f  add     [rcx+rbx+80h], rax
0x1800132a7  mov     rax, [rbp+110h+var_110]
0x1800132ab  mov     [rsi+rdi+80h], rax
0x1800132b3  movsxd  rax, dword ptr [rdi+158h]
0x1800132ba  imul    rcx, rax, 160h
0x1800132c1  mov     rax, [rbp+110h+var_40]
0x1800132c8  sub     rax, [rsi+rdi+150h]
0x1800132d0  add     [rcx+rbx+150h], rax
0x1800132d8  mov     rax, [rbp+110h+var_40]
0x1800132df  mov     [rsi+rdi+150h], rax
0x1800132e7  movsxd  rax, dword ptr [rdi+158h]
0x1800132ee  imul    rcx, rax, 160h
0x1800132f5  mov     rax, [rbp+110h+var_80]
0x1800132fc  sub     rax, [rsi+rdi+110h]
0x180013304  add     [rcx+rbx+110h], rax
0x18001330c  mov     rax, [rbp+110h+var_80]
0x180013313  mov     [rsi+rdi+110h], rax
0x18001331b  movsxd  rax, dword ptr [rdi+158h]
0x180013322  imul    rcx, rax, 160h
0x180013329  mov     rax, [rbp+110h+var_108]
0x18001332d  sub     rax, [rsi+rdi+88h]
0x180013335  add     [rcx+rbx+88h], rax
0x18001333d  mov     rax, [rbp+110h+var_108]
0x180013341  mov     [rsi+rdi+88h], rax
0x180013349  movsxd  rax, dword ptr [rdi+158h]
0x180013350  imul    rcx, rax, 160h
0x180013357  mov     rax, [rbp+110h+var_38]
0x18001335e  sub     rax, [rsi+rdi+158h]
0x180013366  add     [rcx+rbx+158h], rax
0x18001336e  mov     rax, [rbp+110h+var_38]
0x180013375  mov     [rsi+rdi+158h], rax
0x18001337d  movsxd  rax, dword ptr [rdi+158h]
0x180013384  imul    rcx, rax, 160h
0x18001338b  mov     rax, [rbp+110h+var_78]
0x180013392  sub     rax, [rsi+rdi+118h]
0x18001339a  add     [rcx+rbx+118h], rax
0x1800133a2  mov     rax, [rbp+110h+var_78]
0x1800133a9  mov     [rsi+rdi+118h], rax
0x1800133b1  jmp     loc_180012D4B
0x1800133b6  cmp     ebx, 8
0x1800133b9  jnz     short loc_1800133D1
0x1800133bb  mov     rcx, [rdi+0C8h]
0x1800133c2  mov     eax, 0F20h
0x1800133c7  mov     esi, 0DC0h
0x1800133cc  jmp     loc_180012D46
0x1800133d1  mov     eax, 0C000000Dh
0x1800133d6  jmp     loc_180012D4D
```
