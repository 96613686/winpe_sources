# UIComposition::UpdateFont(IMCLock &)

- ea: `0x18006e2dc`
- end: `0x18006e4fe`
- name: `?UpdateFont@UIComposition@@AEAAJAEAVIMCLock@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a9e0`
- `0x1800e3960`

## callees

- `0x18001cc80`
- `0x18006e2dc`
- `0x18009eaea`
- `0x18009eb02`
- `0x180106a60`

## import_xrefs

- `USER32!SystemParametersInfoForDpi` at `0x18006e45c`
- `USER32!SystemParametersInfoForDpi` at `0x18006e45c`
- `USER32!GetDpiForWindow` at `0x18006e42c`
- `USER32!GetDpiForWindow` at `0x18006e42c`
- `GDI32!DeleteObject` at `0x18006e3b3`
- `GDI32!DeleteObject` at `0x18006e3c5`
- `GDI32!DeleteObject` at `0x18006e3b3`
- `GDI32!DeleteObject` at `0x18006e3c5`
- `GDI32!CreateFontIndirectW` at `0x18006e418`
- `GDI32!CreateFontIndirectW` at `0x18006e4b3`
- `GDI32!CreateFontIndirectW` at `0x18006e418`
- `GDI32!CreateFontIndirectW` at `0x18006e4b3`

## string_xrefs

- `0x18006e4c9`: `UIComposition::UpdateFont. imc==NULL`

## pseudocode

```c
__int64 __fastcall UIComposition::UpdateFont(UIComposition *this, struct IMCLock *a2)
{
  _OWORD *v5; // rax
  int v6; // ebx
  void *v7; // rcx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  LOGFONTW lf; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[404]; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v16; // [rsp+228h] [rbp+128h]
  __int128 v17; // [rsp+238h] [rbp+138h]
  __int128 v18; // [rsp+248h] [rbp+148h]
  __int128 v19; // [rsp+258h] [rbp+158h]
  _OWORD v20[2]; // [rsp+268h] [rbp+168h]

  if ( *((_QWORD *)this + 75)
    && *((_QWORD *)this + 77)
    && !memcmp_0((char *)this + 680, (const void *)(*((_QWORD *)a2 + 1) + 36LL), 0x5Cu) )
  {
    return 1;
  }
  v5 = (_OWORD *)*((_QWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 680) = *(_OWORD *)((char *)v5 + 36);
  *(_OWORD *)((char *)this + 696) = *(_OWORD *)((char *)v5 + 52);
  *(_OWORD *)((char *)this + 712) = *(_OWORD *)((char *)v5 + 68);
  *(_OWORD *)((char *)this + 728) = *(_OWORD *)((char *)v5 + 84);
  *(_OWORD *)((char *)this + 744) = *(_OWORD *)((char *)v5 + 100);
  *(_OWORD *)((char *)this + 756) = v5[7];
  if ( !*((_QWORD *)a2 + 1) )
  {
    v6 = -2147467259;
    goto LABEL_15;
  }
  v6 = *((_DWORD *)a2 + 6);
  if ( v6 < 0 )
  {
LABEL_15:
    CicTrace(2u, "UIComposition::UpdateFont. imc==NULL");
    return (unsigned int)v6;
  }
  if ( *((_QWORD *)this + 75) )
    DeleteObject(*((HGDIOBJ *)this + 75));
  v7 = (void *)*((_QWORD *)this + 77);
  if ( v7 )
    DeleteObject(v7);
  v8 = *(_OWORD *)((char *)this + 696);
  *(_OWORD *)&lf.lfHeight = *(_OWORD *)((char *)this + 680);
  v9 = *(_OWORD *)((char *)this + 712);
  *(_OWORD *)&lf.lfWeight = v8;
  v10 = *(_OWORD *)((char *)this + 728);
  *(_OWORD *)&lf.lfFaceName[2] = v9;
  v11 = *(_OWORD *)((char *)this + 744);
  *(_OWORD *)&lf.lfFaceName[10] = v10;
  v12 = *(_OWORD *)((char *)this + 756);
  *(_OWORD *)&lf.lfFaceName[18] = v11;
  *(_OWORD *)&lf.lfFaceName[24] = v12;
  *((_QWORD *)this + 77) = CreateFontIndirectW(&lf);
  GetDpiForWindow(**((_QWORD **)a2 + 1));
  memset_0(v15, 0, 0x1F4u);
  v14 = 504;
  if ( (unsigned int)SystemParametersInfoForDpi(41, 504, &v14) )
  {
    *(_OWORD *)&lf.lfHeight = v16;
    *(_OWORD *)&lf.lfWeight = v17;
    *(_OWORD *)&lf.lfFaceName[2] = v18;
    *(_OWORD *)&lf.lfFaceName[10] = v19;
    *(_OWORD *)&lf.lfFaceName[18] = v20[0];
    *(_OWORD *)&lf.lfFaceName[24] = *(_OWORD *)((char *)v20 + 12);
  }
  *((_QWORD *)this + 75) = CreateFontIndirectW(&lf);
  return 0;
}

```

## disassembly

```asm
0x18006e2dc  mov     [rsp-8+arg_10], rbx
0x18006e2e1  push    rbp
0x18006e2e2  push    rsi
0x18006e2e3  push    rdi
0x18006e2e4  lea     rbp, [rsp-1A0h]
0x18006e2ec  sub     rsp, 2A0h
0x18006e2f3  mov     rax, cs:__security_cookie
0x18006e2fa  xor     rax, rsp
0x18006e2fd  mov     [rbp+1B0h+var_20], rax
0x18006e304  cmp     qword ptr [rcx+258h], 0
0x18006e30c  mov     rsi, rdx
0x18006e30f  mov     rdi, rcx
0x18006e312  jz      short loc_18006E346
0x18006e314  cmp     qword ptr [rcx+268h], 0
0x18006e31c  jz      short loc_18006E346
0x18006e31e  mov     rdx, [rdx+8]
0x18006e322  add     rcx, 2A8h; Buf1
0x18006e329  add     rdx, 24h ; '$'; Buf2
0x18006e32d  mov     r8d, 5Ch ; '\'; Size
0x18006e333  call    memcmp_0
0x18006e338  test    eax, eax
0x18006e33a  jnz     short loc_18006E346
0x18006e33c  mov     eax, 1
0x18006e341  jmp     loc_18006E4DC
0x18006e346  mov     rax, [rsi+8]
0x18006e34a  movups  xmm0, xmmword ptr [rax+24h]
0x18006e34e  movups  xmmword ptr [rdi+2A8h], xmm0
0x18006e355  movups  xmm1, xmmword ptr [rax+34h]
0x18006e359  movups  xmmword ptr [rdi+2B8h], xmm1
0x18006e360  movups  xmm0, xmmword ptr [rax+44h]
0x18006e364  movups  xmmword ptr [rdi+2C8h], xmm0
0x18006e36b  movups  xmm1, xmmword ptr [rax+54h]
0x18006e36f  movups  xmmword ptr [rdi+2D8h], xmm1
0x18006e376  movups  xmm0, xmmword ptr [rax+64h]
0x18006e37a  movups  xmmword ptr [rdi+2E8h], xmm0
0x18006e381  movups  xmm1, xmmword ptr [rax+70h]
0x18006e385  movups  xmmword ptr [rdi+2F4h], xmm1
0x18006e38c  cmp     qword ptr [rsi+8], 0
0x18006e391  jz      loc_18006E4C4
0x18006e397  mov     ebx, [rsi+18h]
0x18006e39a  test    ebx, ebx
0x18006e39c  js      loc_18006E4C9
0x18006e3a2  cmp     qword ptr [rdi+258h], 0
0x18006e3aa  jz      short loc_18006E3B9
0x18006e3ac  mov     rcx, [rdi+258h]; ho
0x18006e3b3  call    cs:__imp_DeleteObject
0x18006e3b9  mov     rcx, [rdi+268h]; ho
0x18006e3c0  test    rcx, rcx
0x18006e3c3  jz      short loc_18006E3CB
0x18006e3c5  call    cs:__imp_DeleteObject
0x18006e3cb  movups  xmm0, xmmword ptr [rdi+2A8h]
0x18006e3d2  lea     rcx, [rsp+2B0h+lf]; lplf
0x18006e3d7  movups  xmm1, xmmword ptr [rdi+2B8h]
0x18006e3de  movaps  xmmword ptr [rsp+2B0h+lf.lfHeight], xmm0
0x18006e3e3  movups  xmm0, xmmword ptr [rdi+2C8h]
0x18006e3ea  movaps  xmmword ptr [rsp+2B0h+lf.lfWeight], xmm1
0x18006e3ef  movups  xmm1, xmmword ptr [rdi+2D8h]
0x18006e3f6  movaps  xmmword ptr [rsp+2B0h+lf.lfFaceName+4], xmm0
0x18006e3fb  movups  xmm0, xmmword ptr [rdi+2E8h]
0x18006e402  movaps  xmmword ptr [rsp+2B0h+lf.lfFaceName+14h], xmm1
0x18006e407  movups  xmm1, xmmword ptr [rdi+2F4h]
0x18006e40e  movaps  xmmword ptr [rsp+2B0h+lf.lfFaceName+24h], xmm0
0x18006e413  movups  xmmword ptr [rsp+2B0h+lf.lfFaceName+30h], xmm1
0x18006e418  call    cs:__imp_CreateFontIndirectW
0x18006e41e  mov     [rdi+268h], rax
0x18006e425  mov     rcx, [rsi+8]
0x18006e429  mov     rcx, [rcx]
0x18006e42c  call    cs:__imp_GetDpiForWindow
0x18006e432  xor     edx, edx; Val
0x18006e434  lea     rcx, [rbp+1B0h+var_21C]; void *
0x18006e438  mov     r8d, 1F4h; Size
0x18006e43e  mov     ebx, eax
0x18006e440  call    memset_0
0x18006e445  xor     r9d, r9d
0x18006e448  mov     [rsp+2B0h+var_290], ebx
0x18006e44c  mov     edx, 1F8h
0x18006e451  lea     r8, [rbp+1B0h+var_220]
0x18006e455  mov     [rbp+1B0h+var_220], edx
0x18006e458  lea     ecx, [r9+29h]
0x18006e45c  call    cs:__imp_SystemParametersInfoForDpi
0x18006e462  test    eax, eax
0x18006e464  jz      short loc_18006E4AE
0x18006e466  movups  xmm0, [rbp+1B0h+var_88]
0x18006e46d  movups  xmm1, [rbp+1B0h+var_78]
0x18006e474  movaps  xmmword ptr [rsp+2B0h+lf.lfHeight], xmm0
0x18006e479  movups  xmm0, [rbp+1B0h+var_68]
0x18006e480  movaps  xmmword ptr [rsp+2B0h+lf.lfWeight], xmm1
0x18006e485  movups  xmm1, [rbp+1B0h+var_58]
0x18006e48c  movaps  xmmword ptr [rsp+2B0h+lf.lfFaceName+4], xmm0
0x18006e491  movups  xmm0, xmmword ptr [rbp+1B0h+var_48]
0x18006e498  movaps  xmmword ptr [rsp+2B0h+lf.lfFaceName+14h], xmm1
0x18006e49d  movups  xmm1, xmmword ptr [rbp+1B0h+var_48+0Ch]
0x18006e4a4  movaps  xmmword ptr [rsp+2B0h+lf.lfFaceName+24h], xmm0
0x18006e4a9  movups  xmmword ptr [rsp+2B0h+lf.lfFaceName+30h], xmm1
0x18006e4ae  lea     rcx, [rsp+2B0h+lf]; lplf
0x18006e4b3  call    cs:__imp_CreateFontIndirectW
0x18006e4b9  mov     [rdi+258h], rax
0x18006e4c0  xor     eax, eax
0x18006e4c2  jmp     short loc_18006E4DC
0x18006e4c4  mov     ebx, 80004005h
0x18006e4c9  lea     rdx, aUicompositionU; "UIComposition::UpdateFont. imc==NULL"
0x18006e4d0  mov     ecx, 2; unsigned int
0x18006e4d5  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18006e4da  mov     eax, ebx
0x18006e4dc  mov     rcx, [rbp+1B0h+var_20]
0x18006e4e3  xor     rcx, rsp; StackCookie
0x18006e4e6  call    __security_check_cookie
0x18006e4eb  mov     rbx, [rsp+2B0h+arg_10]
0x18006e4f3  add     rsp, 2A0h
0x18006e4fa  pop     rdi
0x18006e4fb  pop     rsi
0x18006e4fc  pop     rbp
0x18006e4fd  retn
```
