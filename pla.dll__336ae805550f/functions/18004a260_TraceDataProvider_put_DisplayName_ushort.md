# TraceDataProvider::put_DisplayName(ushort *)

- ea: `0x18004a260`
- end: `0x18004a55b`
- name: `?put_DisplayName@TraceDataProvider@@UEAAJPEAG@Z`
- size: `763`
- prototype: `int(TraceDataProvider *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x1800198b0`
- `0x18004a260`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a528`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a337`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a34d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a34d`

## pseudocode

```c
__int64 __fastcall TraceDataProvider::put_DisplayName(TraceDataProvider *this, unsigned __int16 *a2)
{
  const char *v4; // rdx
  int v5; // r8d
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  GUID *v10; // r9
  unsigned __int16 *v11; // rsi
  __int64 v12; // rax
  int v14; // [rsp+70h] [rbp-90h] BYREF
  GUID v15; // [rsp+80h] [rbp-80h] BYREF
  GUID pclsid; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v17[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v18[64]; // [rsp+120h] [rbp+20h] BYREF

  v14 = *((_DWORD *)this + 14);
  *(_QWORD *)&v15.Data1 = this;
  pclsid = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      (__int64)&g_Eventing,
      (__int64)&PLA_EVENT_METHOD,
      3,
      (__int64)"TraceDataProvider::put_DisplayName");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v11 = 0;
    goto LABEL_27;
  }
  if ( CLSIDFromString(a2, &pclsid) >= 0 )
  {
    v6 = *(_QWORD *)this;
    v15 = pclsid;
    v7 = (*(__int64 (__fastcall **)(TraceDataProvider *, GUID *))(v6 + 80))(this, &v15);
    v8 = v7;
    if ( v7 >= 0 )
    {
      PlaiFreeString(*((BSTR *)this + 9));
      *((_QWORD *)this + 9) = 0;
    }
    else
    {
      v14 = 0;
      v15.Data1 = v7;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v17, 0x4000000000000800uLL);
        v9 = -1;
        do
          ++v9;
        while ( v17[v9] );
        v10 = &v15;
LABEL_16:
        EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v10);
        goto LABEL_28;
      }
    }
    goto LABEL_28;
  }
  v11 = 0;
  if ( !*a2 || (v11 = PlaiAllocStringEx(a2, v4, v5)) != 0 )
  {
LABEL_27:
    v8 = 0;
    PlaiFreeString(*((BSTR *)this + 9));
    *((_QWORD *)this + 9) = v11;
    goto LABEL_28;
  }
  v8 = -2147024882;
  v14 = -2147024882;
  v15.Data1 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v18, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v18[v12] );
    v10 = (GUID *)&v14;
    goto LABEL_16;
  }
LABEL_28:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v8;
}

```

## disassembly

```asm
0x18004a260  mov     [rsp-8+arg_10], rbx
0x18004a265  mov     [rsp-8+arg_18], rsi
0x18004a26a  push    rbp
0x18004a26b  push    rdi
0x18004a26c  push    r12
0x18004a26e  push    r14
0x18004a270  push    r15
0x18004a272  lea     rbp, [rsp-0B0h]
0x18004a27a  sub     rsp, 1B0h
0x18004a281  mov     rax, cs:__security_cookie
0x18004a288  xor     rax, rsp
0x18004a28b  mov     [rbp+0D0h+var_30], rax
0x18004a292  mov     eax, [rcx+38h]
0x18004a295  lea     rsi, aTracedataprovi_9; "TraceDataProvider::put_DisplayName"
0x18004a29c  mov     r15d, 4
0x18004a2a2  mov     [rsp+1D0h+var_160], eax
0x18004a2a6  xor     r14d, r14d
0x18004a2a9  mov     qword ptr [rbp+0D0h+var_150], rcx
0x18004a2ad  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004a2b4  xorps   xmm0, xmm0
0x18004a2b7  mov     rdi, rdx
0x18004a2ba  mov     rbx, rcx
0x18004a2bd  lea     r12d, [r15+1Fh]
0x18004a2c1  movups  xmmword ptr [rbp+0D0h+pclsid.Data1], xmm0
0x18004a2c5  jz      short loc_18004A32D
0x18004a2c7  mov     rdx, 4000000000000400h
0x18004a2d1  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004a2d8  jz      short loc_18004A32D
0x18004a2da  mov     rax, cs:qword_180169748
0x18004a2e1  and     rax, rdx
0x18004a2e4  cmp     cs:qword_180169748, rax
0x18004a2eb  jnz     short loc_18004A32D
0x18004a2ed  mov     [rsp+1D0h+var_190], r15
0x18004a2f2  lea     rax, [rsp+1D0h+var_160]
0x18004a2f7  mov     [rsp+1D0h+var_198], rax
0x18004a2fc  lea     r8d, [r15-1]
0x18004a300  lea     rax, [rbp+0D0h+var_150]
0x18004a304  mov     [rsp+1D0h+var_1A0], 8
0x18004a30d  mov     [rsp+1D0h+var_1A8], rax
0x18004a312  lea     rdx, PLA_EVENT_METHOD
0x18004a319  mov     r9, rsi
0x18004a31c  mov     [rsp+1D0h+var_1B0], r12
0x18004a321  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004a328  call    EventingWriteEvent
0x18004a32d  cmp     [rbx+8], r14d
0x18004a331  jz      short loc_18004A33D
0x18004a333  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004a337  call    cs:__imp_EnterCriticalSection
0x18004a33d  test    rdi, rdi
0x18004a340  jz      loc_18004A50B
0x18004a346  lea     rdx, [rbp+0D0h+pclsid]; pclsid
0x18004a34a  mov     rcx, rdi; lpsz
0x18004a34d  call    cs:__imp_CLSIDFromString
0x18004a353  test    eax, eax
0x18004a355  js      loc_18004A45B
0x18004a35b  mov     rax, [rbx]
0x18004a35e  lea     rdx, [rbp+0D0h+var_150]
0x18004a362  movaps  xmm0, xmmword ptr [rbp+0D0h+pclsid.Data1]
0x18004a366  mov     rcx, rbx
0x18004a369  movdqa  [rbp+0D0h+var_150], xmm0
0x18004a36e  mov     rax, [rax+50h]
0x18004a372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a377  mov     edi, eax
0x18004a379  test    eax, eax
0x18004a37b  jns     loc_18004A449
0x18004a381  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004a388  mov     [rsp+1D0h+var_160], r14d
0x18004a38d  mov     dword ptr [rbp+0D0h+var_150], eax
0x18004a390  jz      loc_18004A51E
0x18004a396  mov     rdx, 4000000000000800h; unsigned __int64
0x18004a3a0  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004a3a7  jz      loc_18004A51E
0x18004a3ad  mov     rax, cs:qword_180169748
0x18004a3b4  and     rax, rdx
0x18004a3b7  cmp     cs:qword_180169748, rax
0x18004a3be  jnz     loc_18004A51E
0x18004a3c4  lea     rcx, [rbp+0D0h+var_130]; unsigned __int16 *
0x18004a3c8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004a3cd  lea     rcx, [rbp+0D0h+var_130]
0x18004a3d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a3d5  inc     rax
0x18004a3d8  cmp     [rcx+rax*2], r14w
0x18004a3dd  jnz     short loc_18004A3D5
0x18004a3df  lea     ecx, [rax+rax]
0x18004a3e2  lea     rax, [rbp+0D0h+var_130]
0x18004a3e6  add     rcx, 2
0x18004a3ea  mov     [rsp+1D0h+var_170], rcx
0x18004a3ef  lea     r9, [rbp+0D0h+var_150]
0x18004a3f3  mov     [rsp+1D0h+var_178], rax
0x18004a3f8  lea     rax, [rsp+1D0h+var_160]
0x18004a3fd  mov     [rsp+1D0h+var_180], r12
0x18004a402  mov     [rsp+1D0h+var_188], rsi
0x18004a407  mov     [rsp+1D0h+var_190], r15
0x18004a40c  lea     rdx, PLA_EVENT_ERROR
0x18004a413  mov     [rsp+1D0h+var_198], rax
0x18004a418  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004a41f  lea     rax, byte_180147320
0x18004a426  mov     [rsp+1D0h+var_1A0], 1
0x18004a42f  mov     [rsp+1D0h+var_1A8], rax
0x18004a434  mov     r8d, 5
0x18004a43a  mov     [rsp+1D0h+var_1B0], r15
0x18004a43f  call    EventingWriteEvent
0x18004a444  jmp     loc_18004A51E
0x18004a449  mov     rcx, [rbx+48h]; bstrString
0x18004a44d  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18004a452  mov     [rbx+48h], r14
0x18004a456  jmp     loc_18004A51E
0x18004a45b  mov     rsi, r14
0x18004a45e  cmp     r14w, [rdi]
0x18004a462  jz      loc_18004A50E
0x18004a468  mov     rcx, rdi; unsigned __int16 *
0x18004a46b  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18004a470  mov     rsi, rax
0x18004a473  test    rax, rax
0x18004a476  jnz     loc_18004A50E
0x18004a47c  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004a483  mov     edi, 8007000Eh
0x18004a488  mov     [rsp+1D0h+var_160], edi
0x18004a48c  mov     dword ptr [rbp+0D0h+var_150], r14d
0x18004a490  jz      loc_18004A51E
0x18004a496  mov     rdx, 4000000000000800h; unsigned __int64
0x18004a4a0  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004a4a7  jz      short loc_18004A51E
0x18004a4a9  mov     rax, cs:qword_180169748
0x18004a4b0  and     rax, rdx
0x18004a4b3  cmp     cs:qword_180169748, rax
0x18004a4ba  jnz     short loc_18004A51E
0x18004a4bc  lea     rcx, [rbp+0D0h+var_B0]; unsigned __int16 *
0x18004a4c0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004a4c5  lea     rcx, [rbp+0D0h+var_B0]
0x18004a4c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a4cd  inc     rax
0x18004a4d0  cmp     [rcx+rax*2], r14w
0x18004a4d5  jnz     short loc_18004A4CD
0x18004a4d7  lea     ecx, [rax+rax]
0x18004a4da  lea     rax, [rbp+0D0h+var_B0]
0x18004a4de  add     rcx, 2
0x18004a4e2  mov     [rsp+1D0h+var_170], rcx
0x18004a4e7  lea     r9, [rsp+1D0h+var_160]
0x18004a4ec  mov     [rsp+1D0h+var_178], rax
0x18004a4f1  lea     rax, aTracedataprovi_9; "TraceDataProvider::put_DisplayName"
0x18004a4f8  mov     [rsp+1D0h+var_180], r12
0x18004a4fd  mov     [rsp+1D0h+var_188], rax
0x18004a502  lea     rax, [rbp+0D0h+var_150]
0x18004a506  jmp     loc_18004A407
0x18004a50b  mov     rsi, r14
0x18004a50e  mov     rcx, [rbx+48h]; bstrString
0x18004a512  mov     edi, r14d
0x18004a515  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18004a51a  mov     [rbx+48h], rsi
0x18004a51e  cmp     [rbx+8], r14d
0x18004a522  jz      short loc_18004A52E
0x18004a524  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004a528  call    cs:__imp_LeaveCriticalSection
0x18004a52e  mov     eax, edi
0x18004a530  mov     rcx, [rbp+0D0h+var_30]
0x18004a537  xor     rcx, rsp; StackCookie
0x18004a53a  call    __security_check_cookie
0x18004a53f  lea     r11, [rsp+1D0h+var_20]
0x18004a547  mov     rbx, [r11+40h]
0x18004a54b  mov     rsi, [r11+48h]
0x18004a54f  mov     rsp, r11
0x18004a552  pop     r15
0x18004a554  pop     r14
0x18004a556  pop     r12
0x18004a558  pop     rdi
0x18004a559  pop     rbp
0x18004a55a  retn
```
