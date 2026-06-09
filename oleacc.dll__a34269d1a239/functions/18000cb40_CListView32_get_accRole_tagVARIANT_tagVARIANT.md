# CListView32::get_accRole(tagVARIANT,tagVARIANT *)

- ea: `0x18000cb40`
- end: `0x18000ccc1`
- name: `?get_accRole@CListView32@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CListView32 *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000b890`
- `0x18000baa0`
- `0x18000cb40`
- `0x18000ce1c`
- `0x18000d2b0`
- `0x180019d38`
- `0x180049010`

## import_xrefs

- `USER32!SendMessageW` at `0x18000cc59`
- `USER32!SendMessageW` at `0x18000cc59`

## string_xrefs

- `0x18000ccaf`: `CAccessible::AccSendMessageTimeout`

## pseudocode

```c
__int64 __fastcall CListView32::get_accRole(HWND *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  LONG lVal; // edx
  HWND v7; // rcx
  unsigned int v8; // edx
  unsigned int v9; // r8d
  HWND v10; // rcx
  HWND v11; // rcx
  HWND v12; // r14
  int v13; // eax
  unsigned int v14; // esi
  int v16; // [rsp+28h] [rbp-38h]
  int v17[4]; // [rsp+40h] [rbp-20h] BYREF
  struct _GUID v18; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+40h] BYREF
  int v21; // [rsp+A4h] [rbp+44h]
  __int64 v22; // [rsp+A8h] [rbp+48h] BYREF

  a3->vt = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *))*this + 30))(this) )
    return 2147942487LL;
  lVal = a2->lVal;
  a3->vt = 3;
  if ( !lVal )
  {
    a3->lVal = 33;
    return 0;
  }
  v7 = this[10];
  v19 = 0;
  if ( (unsigned int)LVGetImageIndex(v7, lVal - 1, v17) )
  {
    v10 = this[10];
    v18 = PROPID_ACC_ROLEMAP;
    if ( (unsigned int)CheckDWORDMap(v10, v8, v9, &v18, v17, v16, &v19)
      || (v11 = this[10], v20 = 0, (unsigned int)GetStateImageMapEnt(v11, v17[0], &v20, &v19)) )
    {
      a3->lVal = v19;
      return 0;
    }
  }
  v12 = this[10];
  v20 = *((_DWORD *)this + 25);
  v21 = *((_DWORD *)this + 17);
  v22 = 0;
  v13 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)&v20, v12, 0x1037u, 0, 0, &v22);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( (v22 & 4) != 0 && (unsigned int)SendMessageW(this[10], 0x102Cu, a2->lVal - 1, 61440) )
      a3->lVal = 44;
    else
      a3->lVal = 34;
    return 0;
  }
  Error::IAccessibleError(0, L"CAccessible::AccSendMessageTimeout", v13, v12, 5002);
  return v14;
}

```

## disassembly

```asm
0x18000cb40  mov     [rsp-28h+arg_8], rbx
0x18000cb45  push    rbp
0x18000cb46  push    rsi
0x18000cb47  push    rdi
0x18000cb48  push    r14
0x18000cb4a  push    r15
0x18000cb4c  mov     rbp, rsp
0x18000cb4f  sub     rsp, 60h
0x18000cb53  xor     eax, eax
0x18000cb55  mov     rbx, r8
0x18000cb58  mov     [r8], ax
0x18000cb5c  mov     r15, rdx
0x18000cb5f  mov     rax, [rcx]
0x18000cb62  mov     rdi, rcx
0x18000cb65  mov     rax, [rax+0F0h]
0x18000cb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb71  test    eax, eax
0x18000cb73  jz      loc_18000CC6C
0x18000cb79  mov     edx, [r15+8]
0x18000cb7d  mov     word ptr [rbx], 3
0x18000cb82  test    edx, edx
0x18000cb84  jz      loc_18000CC90
0x18000cb8a  mov     rcx, [rdi+50h]; HWND
0x18000cb8e  lea     r8, [rbp+var_20]; int *
0x18000cb92  dec     edx; int
0x18000cb94  mov     [rbp+arg_0], 0
0x18000cb9b  call    ?LVGetImageIndex@@YAHPEAUHWND__@@HQEAH@Z; LVGetImageIndex(HWND__ *,int,int * const)
0x18000cba0  test    eax, eax
0x18000cba2  jz      short loc_18000CBF6
0x18000cba4  movups  xmm0, xmmword ptr cs:PROPID_ACC_ROLEMAP.Data1
0x18000cbab  mov     rcx, [rdi+50h]; HWND
0x18000cbaf  lea     rax, [rbp+arg_0]
0x18000cbb3  mov     [rsp+60h+var_30], rax; unsigned int *
0x18000cbb8  lea     r9, [rbp+var_10]; struct _GUID *
0x18000cbbc  lea     rax, [rbp+var_20]
0x18000cbc0  mov     [rsp+60h+var_40], rax; int *
0x18000cbc5  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18000cbca  call    ?CheckDWORDMap@@YAHPEAUHWND__@@KKU_GUID@@PEAHHPEAK@Z; CheckDWORDMap(HWND__ *,ulong,ulong,_GUID,int *,int,ulong *)
0x18000cbcf  test    eax, eax
0x18000cbd1  jnz     loc_18000CC99
0x18000cbd7  mov     edx, [rbp+var_20]; int
0x18000cbda  lea     r9, [rbp+arg_0]; unsigned int *
0x18000cbde  mov     rcx, [rdi+50h]; HWND
0x18000cbe2  lea     r8, [rbp+arg_10]; unsigned int *
0x18000cbe6  mov     [rbp+arg_10], eax
0x18000cbe9  call    ?GetStateImageMapEnt@@YAHPEAUHWND__@@HPEAK1@Z; GetStateImageMapEnt(HWND__ *,int,ulong *,ulong *)
0x18000cbee  test    eax, eax
0x18000cbf0  jnz     loc_18000CC99
0x18000cbf6  mov     eax, [rdi+64h]
0x18000cbf9  lea     rcx, [rbp+arg_10]; struct OLEACC_TIMEOUTDATA *
0x18000cbfd  mov     r14, [rdi+50h]
0x18000cc01  xor     r9d, r9d; unsigned __int64
0x18000cc04  mov     [rbp+arg_10], eax
0x18000cc07  mov     r8d, 1037h; unsigned int
0x18000cc0d  mov     eax, [rdi+44h]
0x18000cc10  mov     rdx, r14; HWND
0x18000cc13  mov     [rbp+arg_14], eax
0x18000cc16  lea     rax, [rbp+arg_18]
0x18000cc1a  mov     [rsp+60h+var_38], rax; __int64 *
0x18000cc1f  mov     [rsp+60h+var_40], 0; __int64
0x18000cc28  mov     [rbp+arg_18], 0
0x18000cc30  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18000cc35  mov     esi, eax
0x18000cc37  test    eax, eax
0x18000cc39  js      short loc_18000CCA1
0x18000cc3b  test    byte ptr [rbp+arg_18], 4
0x18000cc3f  jz      short loc_18000CC73
0x18000cc41  mov     eax, [r15+8]
0x18000cc45  mov     edx, 102Ch; Msg
0x18000cc4a  mov     rcx, [rdi+50h]; hWnd
0x18000cc4e  dec     eax
0x18000cc50  movsxd  r8, eax; wParam
0x18000cc53  mov     r9d, 0F000h; lParam
0x18000cc59  call    cs:__imp_SendMessageW
0x18000cc5f  test    eax, eax
0x18000cc61  jz      short loc_18000CC73
0x18000cc63  mov     dword ptr [rbx+8], 2Ch ; ','
0x18000cc6a  jmp     short loc_18000CC7A
0x18000cc6c  mov     eax, 80070057h
0x18000cc71  jmp     short loc_18000CC7C
0x18000cc73  mov     dword ptr [rbx+8], 22h ; '"'
0x18000cc7a  xor     eax, eax
0x18000cc7c  mov     rbx, [rsp+60h+arg_8]
0x18000cc84  add     rsp, 60h
0x18000cc88  pop     r15
0x18000cc8a  pop     r14
0x18000cc8c  pop     rdi
0x18000cc8d  pop     rsi
0x18000cc8e  pop     rbp
0x18000cc8f  retn
0x18000cc90  mov     dword ptr [rbx+8], 21h ; '!'
0x18000cc97  jmp     short loc_18000CC7A
0x18000cc99  mov     eax, [rbp+arg_0]
0x18000cc9c  mov     [rbx+8], eax
0x18000cc9f  jmp     short loc_18000CC7A
0x18000cca1  mov     r9, r14; HWND
0x18000cca4  mov     dword ptr [rsp+60h+var_40], 138Ah; int
0x18000ccac  mov     r8d, esi; int
0x18000ccaf  lea     rdx, aCaccessibleAcc; "CAccessible::AccSendMessageTimeout"
0x18000ccb6  xor     ecx, ecx; struct IUnknown *
0x18000ccb8  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18000ccbd  mov     eax, esi
0x18000ccbf  jmp     short loc_18000CC7C
```
