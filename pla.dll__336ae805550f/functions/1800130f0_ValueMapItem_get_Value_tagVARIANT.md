# ValueMapItem::get_Value(tagVARIANT *)

- ea: `0x1800130f0`
- end: `0x1800133c3`
- name: `?get_Value@ValueMapItem@@UEAAJPEAUtagVARIANT@@@Z`
- size: `723`
- prototype: `int(ValueMapItem *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800130f0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013194`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013153`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013153`
- `OLEAUT32!__imp_VariantInit` at `0x180013165`
- `OLEAUT32!__imp_VariantInit` at `0x180013165`
- `OLEAUT32!__imp_VariantCopy` at `0x18001317a`
- `OLEAUT32!__imp_VariantCopy` at `0x18001317a`

## pseudocode

```c
__int64 __fastcall ValueMapItem::get_Value(ValueMapItem *this, struct tagVARIANT *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // edi
  __int64 v7; // rax
  bool v8; // zf
  ValueMapItem **v9; // r9
  __int64 v10; // rax
  int v11; // [rsp+70h] [rbp-128h] BYREF
  ValueMapItem *v12; // [rsp+78h] [rbp-120h] BYREF
  unsigned __int16 v13[64]; // [rsp+80h] [rbp-118h] BYREF
  unsigned __int16 v14[64]; // [rsp+100h] [rbp-98h] BYREF

  v11 = *((_DWORD *)this + 14);
  v12 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_METHOD, 3, (__int64)"ValueMapItem::get_Value");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    VariantInit(a2);
    a2->llVal = 0;
    v4 = VariantCopy(a2, (const VARIANTARG *)this + 3);
    v5 = v4;
    if ( v4 < 0 )
    {
      v11 = 0;
      LODWORD(v12) = v4;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v13, 0x4000000000000800uLL);
          v7 = -1;
          do
            v8 = v13[++v7] == 0;
          while ( !v8 );
          v9 = &v12;
LABEL_16:
          EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v9);
        }
      }
    }
  }
  else
  {
    v5 = -2147024809;
    v11 = -2147024809;
    LODWORD(v12) = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v14, 0x4000000000000800uLL);
      v10 = -1;
      do
        v8 = v14[++v10] == 0;
      while ( !v8 );
      v9 = (ValueMapItem **)&v11;
      goto LABEL_16;
    }
  }
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v5;
}

```

## disassembly

```asm
0x1800130f0  mov     [rsp+arg_10], rbx
0x1800130f5  mov     [rsp+arg_18], rsi
0x1800130fa  push    rdi
0x1800130fb  sub     rsp, 190h
0x180013102  mov     rax, cs:__security_cookie
0x180013109  xor     rax, rsp
0x18001310c  mov     [rsp+198h+var_18], rax
0x180013114  cmp     dword ptr cs:xmmword_180169738, 0
0x18001311b  lea     rsi, aValuemapitemGe_0; "ValueMapItem::get_Value"
0x180013122  mov     eax, [rcx+38h]
0x180013125  mov     rdi, rdx
0x180013128  mov     [rsp+198h+var_128], eax
0x18001312c  mov     rbx, rcx
0x18001312f  mov     [rsp+198h+var_120], rcx
0x180013134  jz      short loc_180013149
0x180013136  mov     rdx, 4000000000000400h
0x180013140  test    qword ptr cs:xmmword_180169738+8, rdx
0x180013147  jnz     short loc_1800131C1
0x180013149  cmp     dword ptr [rbx+8], 0
0x18001314d  jz      short loc_180013159
0x18001314f  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013153  call    cs:__imp_EnterCriticalSection
0x180013159  test    rdi, rdi
0x18001315c  jz      loc_180013389
0x180013162  mov     rcx, rdi; pvarg
0x180013165  call    cs:__imp_VariantInit
0x18001316b  lea     rdx, [rbx+48h]; pvargSrc
0x18001316f  mov     qword ptr [rdi+8], 0
0x180013177  mov     rcx, rdi; pvargDest
0x18001317a  call    cs:__imp_VariantCopy
0x180013180  mov     edi, eax
0x180013182  test    eax, eax
0x180013184  js      loc_180013354
0x18001318a  cmp     dword ptr [rbx+8], 0
0x18001318e  jz      short loc_18001319A
0x180013190  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013194  call    cs:__imp_LeaveCriticalSection
0x18001319a  mov     eax, edi
0x18001319c  mov     rcx, [rsp+198h+var_18]
0x1800131a4  xor     rcx, rsp; StackCookie
0x1800131a7  call    __security_check_cookie
0x1800131ac  lea     r11, [rsp+198h+var_8]
0x1800131b4  mov     rbx, [r11+20h]
0x1800131b8  mov     rsi, [r11+28h]
0x1800131bc  mov     rsp, r11
0x1800131bf  pop     rdi
0x1800131c0  retn
0x1800131c1  mov     rax, cs:qword_180169748
0x1800131c8  and     rax, rdx
0x1800131cb  cmp     cs:qword_180169748, rax
0x1800131d2  jnz     loc_180013149
0x1800131d8  mov     [rsp+198h+var_158], 4
0x1800131e1  lea     rax, [rsp+198h+var_128]
0x1800131e6  mov     [rsp+198h+var_160], rax
0x1800131eb  lea     rdx, PLA_EVENT_METHOD
0x1800131f2  lea     rax, [rsp+198h+var_120]
0x1800131f7  mov     [rsp+198h+var_168], 8
0x180013200  mov     [rsp+198h+var_170], rax
0x180013205  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18001320c  mov     r9, rsi
0x18001320f  mov     [rsp+198h+var_178], 18h
0x180013218  mov     r8d, 3
0x18001321e  call    EventingWriteEvent
0x180013223  jmp     loc_180013149
0x180013228  mov     rax, cs:qword_180169748
0x18001322f  and     rax, rdx
0x180013232  cmp     cs:qword_180169748, rax
0x180013239  jnz     loc_18001318A
0x18001323f  lea     rcx, [rsp+198h+var_118]; unsigned __int16 *
0x180013247  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001324c  lea     rcx, [rsp+198h+var_118]
0x180013254  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001325b  nop     dword ptr [rax+rax+00h]
0x180013260  cmp     word ptr [rcx+rax*2+2], 0
0x180013266  lea     rax, [rax+1]
0x18001326a  jnz     short loc_180013260
0x18001326c  lea     ecx, [rax+rax]
0x18001326f  lea     rax, [rsp+198h+var_118]
0x180013277  add     rcx, 2
0x18001327b  mov     [rsp+198h+var_138], rcx
0x180013280  lea     r9, [rsp+198h+var_120]
0x180013285  mov     [rsp+198h+var_140], rax
0x18001328a  lea     rax, [rsp+198h+var_128]
0x18001328f  mov     [rsp+198h+var_148], 18h
0x180013298  lea     rdx, PLA_EVENT_ERROR
0x18001329f  mov     [rsp+198h+var_150], rsi
0x1800132a4  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800132ab  mov     [rsp+198h+var_158], 4
0x1800132b4  mov     r8d, 5
0x1800132ba  mov     [rsp+198h+var_160], rax
0x1800132bf  lea     rax, byte_180147320
0x1800132c6  mov     [rsp+198h+var_168], 1
0x1800132cf  mov     [rsp+198h+var_170], rax
0x1800132d4  mov     [rsp+198h+var_178], 4
0x1800132dd  call    EventingWriteEvent
0x1800132e2  jmp     loc_18001318A
0x1800132e7  mov     rax, cs:qword_180169748
0x1800132ee  and     rax, rdx
0x1800132f1  cmp     cs:qword_180169748, rax
0x1800132f8  jnz     loc_18001318A
0x1800132fe  lea     rcx, [rsp+198h+var_98]; unsigned __int16 *
0x180013306  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001330b  lea     rcx, [rsp+198h+var_98]
0x180013313  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001331a  nop     word ptr [rax+rax+00h]
0x180013320  cmp     word ptr [rcx+rax*2+2], 0
0x180013326  lea     rax, [rax+1]
0x18001332a  jnz     short loc_180013320
0x18001332c  lea     ecx, [rax+rax]
0x18001332f  lea     rax, [rsp+198h+var_98]
0x180013337  add     rcx, 2
0x18001333b  mov     [rsp+198h+var_138], rcx
0x180013340  lea     r9, [rsp+198h+var_128]
0x180013345  mov     [rsp+198h+var_140], rax
0x18001334a  lea     rax, [rsp+198h+var_120]
0x18001334f  jmp     loc_18001328F
0x180013354  cmp     dword ptr cs:xmmword_180169738, 0
0x18001335b  mov     [rsp+198h+var_128], 0
0x180013363  mov     dword ptr [rsp+198h+var_120], eax
0x180013367  jz      loc_18001318A
0x18001336d  mov     rdx, 4000000000000800h; unsigned __int64
0x180013377  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001337e  jz      loc_18001318A
0x180013384  jmp     loc_180013228
0x180013389  cmp     dword ptr cs:xmmword_180169738, 0
0x180013390  mov     edi, 80070057h
0x180013395  mov     [rsp+198h+var_128], edi
0x180013399  mov     dword ptr [rsp+198h+var_120], 0
0x1800133a1  jz      loc_18001318A
0x1800133a7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800133b1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800133b8  jz      loc_18001318A
0x1800133be  jmp     loc_1800132E7
```
