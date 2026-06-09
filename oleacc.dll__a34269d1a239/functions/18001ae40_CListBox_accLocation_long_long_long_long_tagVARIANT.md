# CListBox::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x18001ae40`
- end: `0x18001afb4`
- name: `?accLocation@CListBox@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(CListBox *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000b890`
- `0x18000baa0`
- `0x18001ae40`
- `0x18001c430`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `USER32!MapWindowPoints` at `0x18001af6e`
- `USER32!MapWindowPoints` at `0x18001af6e`

## string_xrefs

- `0x18001af3e`: `CAccessible::AccSendMessageTimeout`

## pseudocode

```c
__int64 __fastcall CListBox::accLocation(CListBox *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  __int64 v9; // rax
  LONG lVal; // ecx
  IRecordInfo *pRecInfo; // xmm1_8
  HWND v14; // rsi
  int v15; // eax
  unsigned int v16; // edi
  LONG y; // edx
  int v18; // eax
  _DWORD v19[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v20; // [rsp+38h] [rbp-41h] BYREF
  struct tagVARIANT v21; // [rsp+40h] [rbp-39h] BYREF
  struct tagPOINT Points[2]; // [rsp+60h] [rbp-19h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = *(_QWORD *)this;
  *(_OWORD *)&Points[0].x = 0;
  if ( !(*(unsigned int (__fastcall **)(CListBox *, struct tagVARIANT *))(v9 + 240))(this, a6) )
    return 2147942487LL;
  lVal = a6->lVal;
  if ( lVal )
  {
    v19[0] = *((_DWORD *)this + 25);
    v19[1] = *((_DWORD *)this + 17);
    v20 = 0;
    v14 = (HWND)*((_QWORD *)this + 10);
    v15 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)v19, v14, 0x198u, lVal - 1, (__int64)Points, &v20);
    v16 = v15;
    if ( v15 >= 0 )
    {
      if ( v20 == -1 )
      {
        return 2147500037LL;
      }
      else
      {
        MapWindowPoints(*((HWND *)this + 10), 0, Points, 2u);
        y = Points[0].y;
        v18 = Points[1].x - Points[0].x;
        *a2 = Points[0].x;
        *a3 = y;
        *a4 = v18;
        *a5 = Points[1].y - y;
        return 0;
      }
    }
    else
    {
      Error::IAccessibleError(0, L"CAccessible::AccSendMessageTimeout", v15, v14, 5002);
      return v16;
    }
  }
  else
  {
    pRecInfo = a6->pRecInfo;
    *(_OWORD *)&v21.vt = *(_OWORD *)&a6->vt;
    v21.pRecInfo = pRecInfo;
    return CClient::accLocation((HWND *)this, a2, a3, a4, a5, &v21);
  }
}

```

## disassembly

```asm
0x18001ae40  push    rbp
0x18001ae42  push    rbx
0x18001ae43  push    rsi
0x18001ae44  push    rdi
0x18001ae45  push    r12
0x18001ae47  push    r13
0x18001ae49  push    r14
0x18001ae4b  push    r15
0x18001ae4d  lea     rbp, [rsp-0Fh]
0x18001ae52  sub     rsp, 88h
0x18001ae59  mov     rax, cs:__security_cookie
0x18001ae60  xor     rax, rsp
0x18001ae63  mov     [rbp+47h+var_50], rax
0x18001ae67  mov     r13, [rbp+47h+arg_20]
0x18001ae6b  xor     esi, esi
0x18001ae6d  mov     rdi, [rbp+47h+arg_28]
0x18001ae71  mov     r14, rdx
0x18001ae74  mov     [rdx], esi
0x18001ae76  xorps   xmm0, xmm0
0x18001ae79  mov     [r8], esi
0x18001ae7c  mov     rdx, rdi
0x18001ae7f  mov     [r9], esi
0x18001ae82  mov     r12, r9
0x18001ae85  mov     [r13+0], esi
0x18001ae89  mov     r15, r8
0x18001ae8c  mov     rax, [rcx]
0x18001ae8f  mov     rbx, rcx
0x18001ae92  movups  xmmword ptr [rbp+47h+Points.x], xmm0
0x18001ae96  mov     rax, [rax+0F0h]
0x18001ae9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aea2  test    eax, eax
0x18001aea4  jnz     short loc_18001AEB0
0x18001aea6  mov     eax, 80070057h
0x18001aeab  jmp     loc_18001AF94
0x18001aeb0  mov     ecx, [rdi+8]
0x18001aeb3  test    ecx, ecx
0x18001aeb5  jnz     short loc_18001AEEC
0x18001aeb7  movups  xmm0, xmmword ptr [rdi]
0x18001aeba  lea     rax, [rbp+47h+var_80]
0x18001aebe  mov     r9, r12; int *
0x18001aec1  movsd   xmm1, qword ptr [rdi+10h]
0x18001aec6  mov     r8, r15; int *
0x18001aec9  mov     [rsp+0C0h+var_98], rax; struct tagVARIANT *
0x18001aece  mov     rdx, r14; int *
0x18001aed1  mov     rcx, rbx; this
0x18001aed4  movaps  xmmword ptr [rbp+47h+var_80], xmm0
0x18001aed8  movsd   qword ptr [rbp+47h+var_80+10h], xmm1
0x18001aedd  mov     [rsp+0C0h+var_A0], r13; int *
0x18001aee2  call    ?accLocation@CClient@@UEAAJPEAJ000UtagVARIANT@@@Z; CClient::accLocation(long *,long *,long *,long *,tagVARIANT)
0x18001aee7  jmp     loc_18001AF94
0x18001aeec  mov     eax, [rbx+64h]
0x18001aeef  mov     r8d, 198h; unsigned int
0x18001aef5  mov     [rbp+47h+var_90], eax
0x18001aef8  mov     eax, [rbx+44h]
0x18001aefb  mov     [rbp+47h+var_8C], eax
0x18001aefe  lea     eax, [rcx-1]
0x18001af01  movsxd  r9, eax; unsigned __int64
0x18001af04  lea     rcx, [rbp+47h+var_90]; struct OLEACC_TIMEOUTDATA *
0x18001af08  lea     rax, [rbp+47h+var_88]
0x18001af0c  mov     [rbp+47h+var_88], rsi
0x18001af10  mov     rsi, [rbx+50h]
0x18001af14  mov     [rsp+0C0h+var_98], rax; __int64 *
0x18001af19  mov     rdx, rsi; HWND
0x18001af1c  lea     rax, [rbp+47h+Points]
0x18001af20  mov     [rsp+0C0h+var_A0], rax; __int64
0x18001af25  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18001af2a  mov     edi, eax
0x18001af2c  test    eax, eax
0x18001af2e  jns     short loc_18001AF50
0x18001af30  mov     r9, rsi; HWND
0x18001af33  mov     dword ptr [rsp+0C0h+var_A0], 138Ah; int
0x18001af3b  mov     r8d, eax; int
0x18001af3e  lea     rdx, aCaccessibleAcc; "CAccessible::AccSendMessageTimeout"
0x18001af45  xor     ecx, ecx; struct IUnknown *
0x18001af47  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18001af4c  mov     eax, edi
0x18001af4e  jmp     short loc_18001AF94
0x18001af50  cmp     [rbp+47h+var_88], 0FFFFFFFFFFFFFFFFh
0x18001af55  jnz     short loc_18001AF5E
0x18001af57  mov     eax, 80004005h
0x18001af5c  jmp     short loc_18001AF94
0x18001af5e  mov     rcx, [rbx+50h]; hWndFrom
0x18001af62  lea     r8, [rbp+47h+Points]; lpPoints
0x18001af66  mov     r9d, 2; cPoints
0x18001af6c  xor     edx, edx; hWndTo
0x18001af6e  call    cs:__imp_MapWindowPoints
0x18001af74  mov     ecx, [rbp+47h+Points.x]
0x18001af77  mov     edx, [rbp+47h+Points.y]
0x18001af7a  mov     eax, [rbp+47h+Points.x+8]
0x18001af7d  sub     eax, ecx
0x18001af7f  mov     [r14], ecx
0x18001af82  mov     [r15], edx
0x18001af85  mov     [r12], eax
0x18001af89  mov     eax, [rbp+47h+Points.y+8]
0x18001af8c  sub     eax, edx
0x18001af8e  mov     [r13+0], eax
0x18001af92  xor     eax, eax
0x18001af94  mov     rcx, [rbp+47h+var_50]
0x18001af98  xor     rcx, rsp; StackCookie
0x18001af9b  call    __security_check_cookie
0x18001afa0  add     rsp, 88h
0x18001afa7  pop     r15
0x18001afa9  pop     r14
0x18001afab  pop     r13
0x18001afad  pop     r12
0x18001afaf  pop     rdi
0x18001afb0  pop     rsi
0x18001afb1  pop     rbx
0x18001afb2  pop     rbp
0x18001afb3  retn
```
