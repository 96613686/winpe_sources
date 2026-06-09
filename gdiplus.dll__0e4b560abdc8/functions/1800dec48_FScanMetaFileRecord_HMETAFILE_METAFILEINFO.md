# FScanMetaFileRecord(HMETAFILE__ *,METAFILEINFO *)

- ea: `0x1800dec48`
- end: `0x1800ded7c`
- name: `?FScanMetaFileRecord@@YAHPEAUHMETAFILE__@@PEAUMETAFILEINFO@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(HMETAFILE hmf, struct METAFILEINFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a6a9c`

## callees

- `0x1800dec48`
- `0x1800e9380`

## import_xrefs

- `GDI32!EnumMetaFile` at `0x1800decbc`
- `GDI32!EnumMetaFile` at `0x1800decbc`
- `GDI32!DeleteDC` at `0x1800ded48`
- `GDI32!DeleteDC` at `0x1800ded48`
- `GDI32!CreateCompatibleDC` at `0x1800dec73`
- `GDI32!CreateCompatibleDC` at `0x1800dec73`

## pseudocode

```c
HDC __fastcall FScanMetaFileRecord(HMETAFILE hmf, struct METAFILEINFO *a2)
{
  HDC result; // rax
  HDC v5; // rbx
  char v6; // cl
  int v7; // eax
  int v8; // edx
  LPARAM v9; // xmm1_8
  LPARAM param[6]; // [rsp+20h] [rbp-40h] BYREF

  result = CreateCompatibleDC(0);
  v5 = result;
  if ( !result )
    return result;
  memset(param, 0, 44);
  LODWORD(param[0]) = 0;
  LOWORD(param[3]) = 1;
  EnumMetaFile(result, hmf, WmfScanProc, (LPARAM)param);
  v6 = param[3];
  if ( (param[3] & 1) != 0 )
  {
    if ( (param[3] & 2) == 0 )
    {
      if ( (param[3] & 4) != 0 )
      {
LABEL_8:
        v7 = HIDWORD(param[1]);
        if ( param[1] < 0 )
        {
          v7 = -HIDWORD(param[1]);
          HIDWORD(param[1]) = -HIDWORD(param[1]);
        }
        v8 = param[2];
        if ( SLODWORD(param[2]) < 0 )
        {
          v8 = -LODWORD(param[2]);
          LODWORD(param[2]) = -LODWORD(param[2]);
        }
        goto LABEL_13;
      }
      if ( (param[3] & 0x30) == 0x10 )
        *(_OWORD *)((char *)param + 4) = *(_OWORD *)((char *)&param[3] + 4);
    }
    if ( (param[3] & 4) != 0 )
      goto LABEL_8;
  }
  v8 = param[2];
  v7 = HIDWORD(param[1]);
LABEL_13:
  if ( !v7 || !v8 )
  {
    v6 = param[3] & 0xFE;
    LOWORD(param[3]) &= ~1u;
  }
  if ( (v6 & 1) != 0 )
  {
    v9 = param[2];
    *(_OWORD *)a2 = *(_OWORD *)param;
    *((_QWORD *)a2 + 2) = v9;
  }
  DeleteDC(v5);
  return (HDC)(param[3] & 1);
}

```

## disassembly

```asm
0x1800dec48  mov     [rsp-18h+arg_10], rbx
0x1800dec4d  mov     [rsp-18h+arg_18], rsi
0x1800dec52  push    rbp
0x1800dec53  push    rdi
0x1800dec54  push    r14
0x1800dec56  mov     rbp, rsp
0x1800dec59  sub     rsp, 60h
0x1800dec5d  mov     rax, cs:__security_cookie
0x1800dec64  xor     rax, rsp
0x1800dec67  mov     [rbp+var_10], rax
0x1800dec6b  mov     rsi, rcx
0x1800dec6e  mov     rdi, rdx
0x1800dec71  xor     ecx, ecx; hdc
0x1800dec73  call    cs:__imp_CreateCompatibleDC
0x1800dec7a  nop     dword ptr [rax+rax+00h]
0x1800dec7f  mov     rbx, rax
0x1800dec82  test    rax, rax
0x1800dec85  jz      loc_1800DED5A
0x1800dec8b  xor     eax, eax
0x1800dec8d  lea     r9, [rbp+param]; param
0x1800dec91  xorps   xmm0, xmm0
0x1800dec94  mov     qword ptr [rbp+var_30+10h], rax
0x1800dec98  movups  xmmword ptr [rbp+param], xmm0
0x1800dec9c  and     dword ptr [rbp+param], eax
0x1800dec9f  lea     r8, ?WmfScanProc@@YAHPEAUHDC__@@PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z; proc
0x1800deca6  lea     r14d, [rax+1]
0x1800decaa  mov     dword ptr [rbp+var_30+18h], eax
0x1800decad  movups  xmmword ptr [rbp+var_30], xmm0
0x1800decb1  mov     rdx, rsi; hmf
0x1800decb4  mov     word ptr [rbp+var_30+8], r14w
0x1800decb9  mov     rcx, rbx; hdc
0x1800decbc  call    cs:__imp_EnumMetaFile
0x1800decc3  nop     dword ptr [rax+rax+00h]
0x1800decc8  mov     cl, [rbp+var_30+8]
0x1800deccb  test    r14b, cl
0x1800decce  jz      short loc_1800DED11
0x1800decd0  test    cl, 2
0x1800decd3  jnz     short loc_1800DECF2
0x1800decd5  test    cl, 4
0x1800decd8  jnz     short loc_1800DECF7
0x1800decda  mov     al, cl
0x1800decdc  and     al, 30h
0x1800decde  cmp     al, 10h
0x1800dece0  jnz     short loc_1800DECF2
0x1800dece2  mov     rax, qword ptr [rbp+var_30+14h]
0x1800dece6  mov     [rbp+param+0Ch], rax
0x1800decea  mov     rax, qword ptr [rbp+var_30+0Ch]
0x1800decee  mov     [rbp+param+4], rax
0x1800decf2  test    cl, 4
0x1800decf5  jz      short loc_1800DED11
0x1800decf7  mov     eax, dword ptr [rbp+param+0Ch]
0x1800decfa  test    eax, eax
0x1800decfc  jns     short loc_1800DED03
0x1800decfe  neg     eax
0x1800ded00  mov     dword ptr [rbp+param+0Ch], eax
0x1800ded03  mov     edx, dword ptr [rbp+var_30]
0x1800ded06  test    edx, edx
0x1800ded08  jns     short loc_1800DED17
0x1800ded0a  neg     edx
0x1800ded0c  mov     dword ptr [rbp+var_30], edx
0x1800ded0f  jmp     short loc_1800DED17
0x1800ded11  mov     edx, dword ptr [rbp+var_30]
0x1800ded14  mov     eax, dword ptr [rbp+param+0Ch]
0x1800ded17  test    eax, eax
0x1800ded19  jz      short loc_1800DED1F
0x1800ded1b  test    edx, edx
0x1800ded1d  jnz     short loc_1800DED2F
0x1800ded1f  movzx   ecx, word ptr [rbp+var_30+8]
0x1800ded23  mov     eax, 0FFFEh
0x1800ded28  and     cx, ax
0x1800ded2b  mov     word ptr [rbp+var_30+8], cx
0x1800ded2f  test    r14b, cl
0x1800ded32  jz      short loc_1800DED45
0x1800ded34  movups  xmm0, xmmword ptr [rbp+param]
0x1800ded38  movsd   xmm1, qword ptr [rbp+var_30]
0x1800ded3d  movups  xmmword ptr [rdi], xmm0
0x1800ded40  movsd   qword ptr [rdi+10h], xmm1
0x1800ded45  mov     rcx, rbx; hdc
0x1800ded48  call    cs:__imp_DeleteDC
0x1800ded4f  nop     dword ptr [rax+rax+00h]
0x1800ded54  mov     eax, dword ptr [rbp+var_30+8]
0x1800ded57  and     eax, r14d
0x1800ded5a  mov     rcx, [rbp+var_10]
0x1800ded5e  xor     rcx, rsp; StackCookie
0x1800ded61  call    __security_check_cookie
0x1800ded66  lea     r11, [rsp+60h+var_s0]
0x1800ded6b  mov     rbx, [r11+30h]
0x1800ded6f  mov     rsi, [r11+38h]
0x1800ded73  mov     rsp, r11
0x1800ded76  pop     r14
0x1800ded78  pop     rdi
0x1800ded79  pop     rbp
0x1800ded7a  retn
```
