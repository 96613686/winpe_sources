# AssembleOutputXML(ulong,ulong,ushort const *,ushort * *)

- ea: `0x180006000`
- end: `0x180006323`
- name: `?AssembleOutputXML@@YAJKKPEBGPEAPEAG@Z`
- size: `803`
- prototype: `int(unsigned int, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006634`

## callees

- `0x180001660`
- `0x180001fea`
- `0x180005050`
- `0x180005114`
- `0x180006000`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000621f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000621f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062ea`

## string_xrefs

- `0x18000603f`: `<?xml version="1.0" encoding="utf-16"?><SyncML><SyncHdr/><SyncBody><Status><CmdID>1</CmdID><MsgRef>%d</MsgRef><CmdRef>0</CmdRef><Cmd>SyncHdr</Cmd><Data>%d</Data></Status>`

## pseudocode

```c
__int64 __fastcall AssembleOutputXML(__int64 a1, __int64 a2, const unsigned __int16 *a3, unsigned __int16 **a4)
{
  unsigned __int16 *v4; // rcx
  const wchar_t *v6; // rax
  __int64 v8; // rdx
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v20; // rax
  unsigned __int16 *v21; // rsi
  signed int v22; // ebx
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // r8d
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  const unsigned __int16 *v28; // rax
  __int64 v29; // r10
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rdi
  unsigned __int16 *v32; // rax
  __int64 v33; // rax
  unsigned __int16 *v34; // rcx
  unsigned __int64 v35; // rdx
  unsigned __int16 *v36; // r9
  unsigned __int16 *v37; // rcx
  SIZE_T uBytes; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v40[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v41; // [rsp+48h] [rbp-B8h]
  _OWORD v42[2]; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v43[192]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v44[176]; // [rsp+200h] [rbp+100h] BYREF

  v4 = v44;
  v6 = L"<?xml version=\"1.0\" encoding=\"utf-16\"?><SyncML><SyncHdr/><SyncBody><Status><CmdID>1</CmdID><MsgRef>%d</MsgRef"
        "><CmdRef>0</CmdRef><Cmd>SyncHdr</Cmd><Data>%d</Data></Status>";
  v8 = 2;
  do
  {
    v9 = *((_OWORD *)v6 + 1);
    *(_OWORD *)v4 = *(_OWORD *)v6;
    v10 = *((_OWORD *)v6 + 2);
    *((_OWORD *)v4 + 1) = v9;
    v11 = *((_OWORD *)v6 + 3);
    *((_OWORD *)v4 + 2) = v10;
    v12 = *((_OWORD *)v6 + 4);
    *((_OWORD *)v4 + 3) = v11;
    v13 = *((_OWORD *)v6 + 5);
    *((_OWORD *)v4 + 4) = v12;
    v14 = *((_OWORD *)v6 + 6);
    *((_OWORD *)v4 + 5) = v13;
    v15 = *((_OWORD *)v6 + 7);
    v6 += 64;
    *((_OWORD *)v4 + 6) = v14;
    *((_OWORD *)v4 + 7) = v15;
    v4 += 64;
    --v8;
  }
  while ( v8 );
  v16 = *((_OWORD *)v6 + 1);
  *(_OWORD *)v4 = *(_OWORD *)v6;
  v17 = *((_OWORD *)v6 + 2);
  *((_OWORD *)v4 + 1) = v16;
  v18 = *((_OWORD *)v6 + 3);
  *((_OWORD *)v4 + 2) = v17;
  v19 = *((_OWORD *)v6 + 4);
  v20 = *(_QWORD *)(v6 + 39);
  *((_OWORD *)v4 + 3) = v18;
  *((_OWORD *)v4 + 4) = v19;
  *(_QWORD *)(v4 + 39) = v20;
  v41 = *(_OWORD *)L"</SyncBody></SyncML>";
  *(_OWORD *)v40 = *(_OWORD *)L"<Final/></SyncBody></SyncML>";
  v42[0] = *(_OWORD *)L"dy></SyncML>";
  *(_OWORD *)((char *)v42 + 10) = *(_OWORD *)L"SyncML>";
  memset_0(v43, 0, 0x17Eu);
  HIDWORD(uBytes) = 0;
  v21 = 0;
  if ( !a4 )
  {
    v22 = -2147024809;
    goto LABEL_37;
  }
  *a4 = 0;
  v22 = StringCchPrintfW(v43, 0xBFu, v44, 1, 200);
  if ( v22 < 0 )
    goto LABEL_37;
  v23 = v43;
  v24 = 0x7FFFFFFF;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v24;
  }
  while ( v24 );
  v22 = -2147024809;
  v25 = v24 == 0 ? 0x80070057 : 0;
  if ( !v24 )
  {
LABEL_10:
    v22 = v25;
    goto LABEL_37;
  }
  v26 = ((0x7FFFFFFF - v24) & -(__int64)(v24 != 0)) + 2;
  if ( v26 < 2 )
    goto LABEL_36;
  if ( !a3 )
    goto LABEL_37;
  v27 = 0x7FFFFFFF;
  v28 = a3;
  do
  {
    if ( !*v28 )
      break;
    ++v28;
    --v27;
  }
  while ( v27 );
  v25 = v27 == 0 ? 0x80070057 : 0;
  v29 = (0x7FFFFFFF - v27) & -(__int64)(v27 != 0);
  if ( !v27 )
    goto LABEL_10;
  v30 = v29 + v26;
  if ( v29 + v26 < v26 || (v31 = v30 + 28, v30 + 28 < v30) )
  {
LABEL_36:
    v22 = -2147024362;
    goto LABEL_37;
  }
  if ( (v31 & 0x80000000) != 0LL )
  {
    v22 = -2102788093;
  }
  else
  {
    LODWORD(uBytes) = 2 * v31;
    v32 = (unsigned __int16 *)LocalAlloc(0, uBytes);
    v21 = v32;
    if ( v32 )
    {
      if ( v31 )
      {
        if ( v31 > 0x7FFFFFFF )
        {
          *v32 = 0;
        }
        else
        {
          v33 = 2147483646;
          v34 = v43;
          v35 = v31;
          v36 = v21;
          do
          {
            if ( !v33 )
              break;
            if ( !*v34 )
              break;
            *v36++ = *v34++;
            --v33;
            --v35;
          }
          while ( v35 );
          v37 = v36 - 1;
          v22 = v35 == 0 ? 0x8007007A : 0;
          if ( v35 )
            v37 = v36;
          *v37 = 0;
          if ( v35 )
          {
            v22 = StringCchCatW(v21, v31, a3);
            if ( v22 >= 0 )
            {
              v22 = StringCchCatW(v21, v31, v40);
              if ( v22 >= 0 )
              {
                *a4 = v21;
                v21 = 0;
              }
            }
          }
        }
      }
    }
    else
    {
      v22 = -2147024882;
    }
  }
LABEL_37:
  LocalFree(v21);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180006000  mov     [rsp-8+arg_0], rbx
0x180006005  push    rbp
0x180006006  push    rsi
0x180006007  push    rdi
0x180006008  push    r12
0x18000600a  push    r13
0x18000600c  push    r14
0x18000600e  push    r15
0x180006010  lea     rbp, [rsp-270h]
0x180006018  sub     rsp, 370h
0x18000601f  mov     rax, cs:__security_cookie
0x180006026  xor     rax, rsp
0x180006029  mov     [rbp+2A0h+var_40], rax
0x180006030  mov     edi, 2
0x180006035  lea     rcx, [rbp+2A0h+var_1A0]
0x18000603c  mov     r14, r8
0x18000603f  lea     rax, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x180006046  mov     r15, r9
0x180006049  mov     edx, edi
0x18000604b  lea     r8d, [rdi+7Eh]
0x18000604f  movups  xmm0, xmmword ptr [rax]
0x180006052  movups  xmm1, xmmword ptr [rax+10h]
0x180006056  movups  xmmword ptr [rcx], xmm0
0x180006059  movups  xmm0, xmmword ptr [rax+20h]
0x18000605d  movups  xmmword ptr [rcx+10h], xmm1
0x180006061  movups  xmm1, xmmword ptr [rax+30h]
0x180006065  movups  xmmword ptr [rcx+20h], xmm0
0x180006069  movups  xmm0, xmmword ptr [rax+40h]
0x18000606d  movups  xmmword ptr [rcx+30h], xmm1
0x180006071  movups  xmm1, xmmword ptr [rax+50h]
0x180006075  movups  xmmword ptr [rcx+40h], xmm0
0x180006079  movups  xmm0, xmmword ptr [rax+60h]
0x18000607d  movups  xmmword ptr [rcx+50h], xmm1
0x180006081  movups  xmm1, xmmword ptr [rax+70h]
0x180006085  add     rax, r8
0x180006088  movups  xmmword ptr [rcx+60h], xmm0
0x18000608c  movups  xmmword ptr [rcx+70h], xmm1
0x180006090  add     rcx, r8
0x180006093  sub     rdx, 1; Val
0x180006097  jnz     short loc_18000604F
0x180006099  movups  xmm0, xmmword ptr [rax]
0x18000609c  mov     r8d, 17Eh; Size
0x1800060a2  movups  xmm1, xmmword ptr [rax+10h]
0x1800060a6  movups  xmmword ptr [rcx], xmm0
0x1800060a9  movups  xmm0, xmmword ptr [rax+20h]
0x1800060ad  movups  xmmword ptr [rcx+10h], xmm1
0x1800060b1  movups  xmm1, xmmword ptr [rax+30h]
0x1800060b5  movups  xmmword ptr [rcx+20h], xmm0
0x1800060b9  movups  xmm0, xmmword ptr [rax+40h]
0x1800060bd  mov     rax, [rax+4Eh]
0x1800060c1  movups  xmmword ptr [rcx+30h], xmm1
0x1800060c5  movups  xmm1, xmmword ptr cs:aFinalSyncbodyS+10h; "</SyncBody></SyncML>"
0x1800060cc  movups  xmmword ptr [rcx+40h], xmm0
0x1800060d0  mov     [rcx+4Eh], rax
0x1800060d4  lea     rcx, [rbp+2A0h+var_320]; void *
0x1800060d8  movups  xmm0, xmmword ptr cs:aFinalSyncbodyS; "<Final/></SyncBody></SyncML>"
0x1800060df  movups  [rsp+3A0h+var_358], xmm1
0x1800060e4  movups  xmm1, xmmword ptr cs:aFinalSyncbodyS+2Ah; "SyncML>"
0x1800060eb  movups  xmmword ptr [rsp+3A0h+var_368], xmm0
0x1800060f0  movups  xmm0, xmmword ptr cs:aFinalSyncbodyS+20h; "dy></SyncML>"
0x1800060f7  movups  xmmword ptr [rsp+3A0h+var_348], xmm0
0x1800060fc  movups  xmmword ptr [rsp+3A0h+var_348+0Ah], xmm1
0x180006101  call    memset_0
0x180006106  xor     r12d, r12d
0x180006109  mov     [rsp+3A0h+uBytes], r12
0x18000610e  mov     esi, r12d
0x180006111  test    r15, r15
0x180006114  jnz     short loc_180006120
0x180006116  mov     ebx, 80070057h
0x18000611b  jmp     loc_1800062E7
0x180006120  mov     r9d, 1
0x180006126  mov     [r15], r12
0x180006129  lea     r8, [rbp+2A0h+var_1A0]; unsigned __int16 *
0x180006130  mov     [rsp+3A0h+var_380], 0C8h
0x180006138  mov     edx, 0BFh; unsigned __int64
0x18000613d  lea     rcx, [rbp+2A0h+var_320]; unsigned __int16 *
0x180006141  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006146  mov     ebx, eax
0x180006148  test    eax, eax
0x18000614a  js      loc_1800062E7
0x180006150  mov     r13d, 7FFFFFFFh
0x180006156  lea     rax, [rbp+2A0h+var_320]
0x18000615a  mov     edx, r13d
0x18000615d  cmp     [rax], r12w
0x180006161  jz      short loc_18000616C
0x180006163  add     rax, rdi
0x180006166  sub     rdx, 1
0x18000616a  jnz     short loc_18000615D
0x18000616c  mov     rax, rdx
0x18000616f  mov     ebx, 80070057h
0x180006174  neg     rax
0x180006177  mov     rcx, r13
0x18000617a  mov     rax, rdx
0x18000617d  sbb     r8d, r8d
0x180006180  sub     rcx, rdx
0x180006183  not     r8d
0x180006186  and     r8d, ebx
0x180006189  neg     rax
0x18000618c  sbb     r9, r9
0x18000618f  and     r9, rcx
0x180006192  test    rdx, rdx
0x180006195  jnz     short loc_18000619F
0x180006197  mov     ebx, r8d
0x18000619a  jmp     loc_1800062E7
0x18000619f  add     r9, rdi
0x1800061a2  cmp     r9, rdi
0x1800061a5  jb      loc_1800062E2
0x1800061ab  test    r14, r14
0x1800061ae  jz      loc_1800062E7
0x1800061b4  mov     rdx, r13
0x1800061b7  mov     rax, r14
0x1800061ba  cmp     [rax], r12w
0x1800061be  jz      short loc_1800061C9
0x1800061c0  add     rax, rdi
0x1800061c3  sub     rdx, 1
0x1800061c7  jnz     short loc_1800061BA
0x1800061c9  mov     rax, rdx
0x1800061cc  mov     rcx, r13
0x1800061cf  neg     rax
0x1800061d2  mov     rax, rdx
0x1800061d5  sbb     r8d, r8d
0x1800061d8  sub     rcx, rdx
0x1800061db  not     r8d
0x1800061de  and     r8d, ebx
0x1800061e1  neg     rax
0x1800061e4  sbb     r10, r10
0x1800061e7  and     r10, rcx
0x1800061ea  test    rdx, rdx
0x1800061ed  jz      short loc_180006197
0x1800061ef  lea     rax, [r10+r9]
0x1800061f3  cmp     rax, r9
0x1800061f6  jb      loc_1800062E2
0x1800061fc  lea     rdi, [rax+1Ch]
0x180006200  cmp     rdi, rax
0x180006203  jb      loc_1800062E2
0x180006209  lea     eax, [rdi+rdi]
0x18000620c  mov     dword ptr [rsp+3A0h+uBytes], eax
0x180006210  test    edi, edi
0x180006212  js      loc_1800062DB
0x180006218  mov     rdx, [rsp+3A0h+uBytes]; uBytes
0x18000621d  xor     ecx, ecx; uFlags
0x18000621f  call    cs:__imp_LocalAlloc
0x180006226  nop     dword ptr [rax+rax+00h]
0x18000622b  mov     rsi, rax
0x18000622e  test    rax, rax
0x180006231  jnz     short loc_18000623D
0x180006233  mov     ebx, 8007000Eh
0x180006238  jmp     loc_1800062E7
0x18000623d  test    rdi, rdi
0x180006240  jz      loc_1800062E7
0x180006246  cmp     rdi, r13
0x180006249  ja      loc_1800062D5
0x18000624f  mov     eax, 7FFFFFFEh
0x180006254  lea     rcx, [rbp+2A0h+var_320]
0x180006258  mov     rdx, rdi
0x18000625b  mov     r9, rsi
0x18000625e  test    rax, rax
0x180006261  jz      short loc_180006282
0x180006263  movzx   r8d, word ptr [rcx]
0x180006267  test    r8w, r8w
0x18000626b  jz      short loc_180006282
0x18000626d  mov     [r9], r8w
0x180006271  add     rcx, 2
0x180006275  add     r9, 2
0x180006279  dec     rax
0x18000627c  sub     rdx, 1
0x180006280  jnz     short loc_18000625E
0x180006282  mov     rax, rdx
0x180006285  lea     rcx, [r9-2]
0x180006289  neg     rax
0x18000628c  sbb     ebx, ebx
0x18000628e  not     ebx
0x180006290  and     ebx, 8007007Ah
0x180006296  test    rdx, rdx
0x180006299  cmovnz  rcx, r9
0x18000629d  mov     [rcx], r12w
0x1800062a1  jz      short loc_1800062E7
0x1800062a3  mov     r8, r14; unsigned __int16 *
0x1800062a6  mov     rdx, rdi; unsigned __int64
0x1800062a9  mov     rcx, rsi; unsigned __int16 *
0x1800062ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800062b1  mov     ebx, eax
0x1800062b3  test    eax, eax
0x1800062b5  js      short loc_1800062E7
0x1800062b7  lea     r8, [rsp+3A0h+var_368]; unsigned __int16 *
0x1800062bc  mov     rdx, rdi; unsigned __int64
0x1800062bf  mov     rcx, rsi; unsigned __int16 *
0x1800062c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800062c7  mov     ebx, eax
0x1800062c9  test    eax, eax
0x1800062cb  js      short loc_1800062E7
0x1800062cd  mov     [r15], rsi
0x1800062d0  mov     rsi, r12
0x1800062d3  jmp     short loc_1800062E7
0x1800062d5  mov     [rax], r12w
0x1800062d9  jmp     short loc_1800062E7
0x1800062db  mov     ebx, 82AA0003h
0x1800062e0  jmp     short loc_1800062E7
0x1800062e2  mov     ebx, 80070216h
0x1800062e7  mov     rcx, rsi; hMem
0x1800062ea  call    cs:__imp_LocalFree
0x1800062f1  nop     dword ptr [rax+rax+00h]
0x1800062f6  mov     eax, ebx
0x1800062f8  mov     rcx, [rbp+2A0h+var_40]
0x1800062ff  xor     rcx, rsp; StackCookie
0x180006302  call    __security_check_cookie
0x180006307  mov     rbx, [rsp+3A0h+arg_0]
0x18000630f  add     rsp, 370h
0x180006316  pop     r15
0x180006318  pop     r14
0x18000631a  pop     r13
0x18000631c  pop     r12
0x18000631e  pop     rdi
0x18000631f  pop     rsi
0x180006320  pop     rbp
0x180006321  retn
```
