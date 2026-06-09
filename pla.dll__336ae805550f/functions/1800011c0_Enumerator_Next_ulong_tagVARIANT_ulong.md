# Enumerator::Next(ulong,tagVARIANT *,ulong *)

- ea: `0x1800011c0`
- end: `0x180001574`
- name: `?Next@Enumerator@@UEAAJKPEAUtagVARIANT@@PEAK@Z`
- size: `948`
- prototype: `__int64 __fastcall(Enumerator *__hidden this, unsigned int, struct tagVARIANT *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011c0`
- `0x180002bd0`
- `0x180004e98`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800012cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800012cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001237`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001237`
- `OLEAUT32!__imp_VariantInit` at `0x180001282`
- `OLEAUT32!__imp_VariantInit` at `0x180001282`
- `OLEAUT32!__imp_VariantCopy` at `0x1800012a2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800012a2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180001254`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180001254`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800012e3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800012e3`

## pseudocode

```c
__int64 __fastcall Enumerator::Next(Enumerator *this, unsigned int a2, struct tagVARIANT *a3, unsigned int *a4)
{
  HRESULT v4; // eax
  unsigned int v9; // esi
  SAFEARRAY *v10; // rcx
  HRESULT v11; // eax
  int v12; // edi
  struct tagVARIANT *v13; // rdi
  HRESULT v14; // eax
  __int64 v16; // rax
  bool v17; // zf
  __int64 v18; // rax
  HRESULT v19; // [rsp+70h] [rbp-168h] BYREF
  Enumerator *v20; // [rsp+78h] [rbp-160h] BYREF
  void *ppvData; // [rsp+80h] [rbp-158h] BYREF
  unsigned __int16 v22[64]; // [rsp+90h] [rbp-148h] BYREF
  unsigned __int16 v23[64]; // [rsp+110h] [rbp-C8h] BYREF

  v4 = *((_DWORD *)this + 14);
  ppvData = 0;
  v19 = v4;
  v20 = this;
  v9 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::Next", 17, &v20, 8, &v19, 4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v10 = (SAFEARRAY *)*((_QWORD *)this + 8);
  if ( !v10 )
  {
    v12 = 0;
LABEL_14:
    if ( a4 )
      *a4 = v9;
    goto LABEL_16;
  }
  v11 = SafeArrayAccessData(v10, &ppvData);
  v12 = v11;
  if ( v11 >= 0 )
  {
    while ( v9 < a2 && *((_DWORD *)this + 18) < *((_DWORD *)this + 19) )
    {
      v13 = &a3[v9];
      if ( v13 )
      {
        VariantInit(&a3[v9]);
        v13->llVal = 0;
      }
      v14 = VariantCopy(&a3[v9], (const VARIANTARG *)ppvData + *((unsigned int *)this + 18));
      v12 = v14;
      if ( v14 < 0 )
      {
        LODWORD(v20) = 0;
        v19 = v14;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v23, 0x4000000000000800uLL);
          v18 = -1;
          do
            v17 = v23[++v18] == 0;
          while ( !v17 );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v19, 4, byte_180147320, 1, &v20, 4);
        }
        goto LABEL_16;
      }
      ++*((_DWORD *)this + 18);
      ++v9;
    }
    goto LABEL_14;
  }
  v19 = 0;
  LODWORD(v20) = v11;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v22, 0x4000000000000800uLL);
    v16 = -1;
    do
      v17 = v22[++v16] == 0;
    while ( !v17 );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v20, 4, byte_180147320, 1, &v19, 4);
  }
LABEL_16:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 8));
  if ( v12 >= 0 && a2 > v9 )
    return 1;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800011c0  mov     [rsp+arg_8], rbx
0x1800011c5  push    rbp
0x1800011c6  push    rsi
0x1800011c7  push    rdi
0x1800011c8  push    r12
0x1800011ca  push    r13
0x1800011cc  push    r14
0x1800011ce  push    r15
0x1800011d0  sub     rsp, 1A0h
0x1800011d7  mov     rax, cs:__security_cookie
0x1800011de  xor     rax, rsp
0x1800011e1  mov     [rsp+1D8h+var_48], rax
0x1800011e9  mov     eax, [rcx+38h]
0x1800011ec  xor     r12d, r12d
0x1800011ef  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800011f6  mov     r14, r9
0x1800011f9  mov     r15, r8
0x1800011fc  mov     [rsp+1D8h+ppvData], r12
0x180001204  mov     ebp, edx
0x180001206  mov     [rsp+1D8h+var_168], eax
0x18000120a  mov     rbx, rcx
0x18000120d  mov     [rsp+1D8h+var_160], rcx
0x180001212  mov     esi, r12d
0x180001215  jz      short loc_18000122E
0x180001217  mov     rdx, 4000000000000400h
0x180001221  test    qword ptr cs:xmmword_180169738+8, rdx
0x180001228  jnz     loc_180001409
0x18000122e  cmp     [rbx+8], esi
0x180001231  jz      short loc_18000123D
0x180001233  lea     rcx, [rbx+10h]; lpCriticalSection
0x180001237  call    cs:__imp_EnterCriticalSection
0x18000123d  mov     rcx, [rbx+40h]; psa
0x180001241  mov     r13d, 1
0x180001247  test    rcx, rcx
0x18000124a  jz      short loc_1800012B9
0x18000124c  lea     rdx, [rsp+1D8h+ppvData]; ppvData
0x180001254  call    cs:__imp_SafeArrayAccessData
0x18000125a  mov     edi, eax
0x18000125c  test    eax, eax
0x18000125e  js      loc_180001320
0x180001264  mov     eax, [rbx+4Ch]
0x180001267  cmp     esi, ebp
0x180001269  jnb     short loc_1800012BC
0x18000126b  cmp     [rbx+48h], eax
0x18000126e  jnb     short loc_1800012BC
0x180001270  mov     eax, esi
0x180001272  lea     rcx, [rax+rax*2]
0x180001276  lea     rdi, [r15+rcx*8]
0x18000127a  test    rdi, rdi
0x18000127d  jz      short loc_18000128C
0x18000127f  mov     rcx, rdi; pvarg
0x180001282  call    cs:__imp_VariantInit
0x180001288  mov     [rdi+8], r12
0x18000128c  mov     eax, [rbx+48h]
0x18000128f  mov     rcx, rdi; pvargDest
0x180001292  lea     rdx, [rax+rax*2]
0x180001296  mov     rax, [rsp+1D8h+ppvData]
0x18000129e  lea     rdx, [rax+rdx*8]; pvargSrc
0x1800012a2  call    cs:__imp_VariantCopy
0x1800012a8  mov     edi, eax
0x1800012aa  test    eax, eax
0x1800012ac  js      loc_18000153A
0x1800012b2  inc     dword ptr [rbx+48h]
0x1800012b5  inc     esi
0x1800012b7  jmp     short loc_180001264
0x1800012b9  mov     edi, r12d
0x1800012bc  test    r14, r14
0x1800012bf  jnz     loc_18000156C
0x1800012c5  cmp     [rbx+8], r12d
0x1800012c9  jz      short loc_1800012D5
0x1800012cb  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800012cf  call    cs:__imp_LeaveCriticalSection
0x1800012d5  cmp     [rsp+1D8h+ppvData], r12
0x1800012dd  jz      short loc_1800012E9
0x1800012df  mov     rcx, [rbx+40h]; psa
0x1800012e3  call    cs:__imp_SafeArrayUnaccessData
0x1800012e9  test    edi, edi
0x1800012eb  js      short loc_1800012F3
0x1800012ed  cmp     ebp, esi
0x1800012ef  cmova   edi, r13d
0x1800012f3  mov     eax, edi
0x1800012f5  mov     rcx, [rsp+1D8h+var_48]
0x1800012fd  xor     rcx, rsp; StackCookie
0x180001300  call    __security_check_cookie
0x180001305  mov     rbx, [rsp+1D8h+arg_8]
0x18000130d  add     rsp, 1A0h
0x180001314  pop     r15
0x180001316  pop     r14
0x180001318  pop     r13
0x18000131a  pop     r12
0x18000131c  pop     rdi
0x18000131d  pop     rsi
0x18000131e  pop     rbp
0x18000131f  retn
0x180001320  cmp     dword ptr cs:xmmword_180169738, esi
0x180001326  mov     [rsp+1D8h+var_168], r12d
0x18000132b  mov     dword ptr [rsp+1D8h+var_160], eax
0x18000132f  jz      short loc_1800012C5
0x180001331  mov     rdx, 4000000000000800h; unsigned __int64
0x18000133b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180001342  jz      short loc_1800012C5
0x180001344  mov     rax, cs:qword_180169748
0x18000134b  and     rax, rdx
0x18000134e  cmp     cs:qword_180169748, rax
0x180001355  jnz     loc_1800012C5
0x18000135b  lea     rcx, [rsp+1D8h+var_148]; unsigned __int16 *
0x180001363  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180001368  lea     rcx, [rsp+1D8h+var_148]
0x180001370  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001377  nop     word ptr [rax+rax+00000000h]
0x180001380  cmp     [rcx+rax*2+2], si
0x180001385  lea     rax, [rax+1]
0x180001389  jnz     short loc_180001380
0x18000138b  lea     ecx, [rax+rax]
0x18000138e  mov     r8d, 5
0x180001394  add     rcx, 2
0x180001398  lea     rax, [rsp+1D8h+var_148]
0x1800013a0  mov     [rsp+1D8h+var_178], rcx
0x1800013a5  lea     r9, [rsp+1D8h+var_160]
0x1800013aa  mov     [rsp+1D8h+var_180], rax
0x1800013af  lea     rdx, PLA_EVENT_ERROR
0x1800013b6  mov     [rsp+1D8h+var_188], 11h
0x1800013bf  lea     rax, aEnumeratorNext; "Enumerator::Next"
0x1800013c6  mov     [rsp+1D8h+var_190], rax
0x1800013cb  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800013d2  mov     [rsp+1D8h+var_198], 4
0x1800013db  lea     rax, [rsp+1D8h+var_168]
0x1800013e0  mov     [rsp+1D8h+var_1A0], rax
0x1800013e5  lea     rax, byte_180147320
0x1800013ec  mov     [rsp+1D8h+var_1A8], r13
0x1800013f1  mov     [rsp+1D8h+var_1B0], rax
0x1800013f6  mov     [rsp+1D8h+var_1B8], 4
0x1800013ff  call    EventingWriteEvent
0x180001404  jmp     loc_1800012C5
0x180001409  mov     rax, cs:qword_180169748
0x180001410  and     rax, rdx
0x180001413  cmp     cs:qword_180169748, rax
0x18000141a  jnz     loc_18000122E
0x180001420  mov     [rsp+1D8h+var_198], 4
0x180001429  lea     rax, [rsp+1D8h+var_168]
0x18000142e  mov     [rsp+1D8h+var_1A0], rax
0x180001433  lea     r9, aEnumeratorNext; "Enumerator::Next"
0x18000143a  lea     rax, [rsp+1D8h+var_160]
0x18000143f  mov     [rsp+1D8h+var_1A8], 8
0x180001448  mov     [rsp+1D8h+var_1B0], rax
0x18000144d  lea     rdx, PLA_EVENT_METHOD
0x180001454  mov     r8d, 3
0x18000145a  mov     [rsp+1D8h+var_1B8], 11h
0x180001463  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18000146a  call    EventingWriteEvent
0x18000146f  jmp     loc_18000122E
0x180001474  mov     rax, cs:qword_180169748
0x18000147b  and     rax, rdx
0x18000147e  cmp     cs:qword_180169748, rax
0x180001485  jnz     loc_1800012C5
0x18000148b  lea     rcx, [rsp+1D8h+var_C8]; unsigned __int16 *
0x180001493  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180001498  lea     rcx, [rsp+1D8h+var_C8]
0x1800014a0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800014a7  nop     word ptr [rax+rax+00000000h]
0x1800014b0  cmp     [rcx+rax*2+2], r12w
0x1800014b6  lea     rax, [rax+1]
0x1800014ba  jnz     short loc_1800014B0
0x1800014bc  lea     ecx, [rax+rax]
0x1800014bf  mov     r8d, 5
0x1800014c5  add     rcx, 2
0x1800014c9  lea     rax, [rsp+1D8h+var_C8]
0x1800014d1  mov     [rsp+1D8h+var_178], rcx
0x1800014d6  lea     r9, [rsp+1D8h+var_168]
0x1800014db  mov     [rsp+1D8h+var_180], rax
0x1800014e0  lea     rdx, PLA_EVENT_ERROR
0x1800014e7  mov     [rsp+1D8h+var_188], 11h
0x1800014f0  lea     rax, aEnumeratorNext; "Enumerator::Next"
0x1800014f7  mov     [rsp+1D8h+var_190], rax
0x1800014fc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180001503  mov     [rsp+1D8h+var_198], 4
0x18000150c  lea     rax, [rsp+1D8h+var_160]
0x180001511  mov     [rsp+1D8h+var_1A0], rax
0x180001516  lea     rax, byte_180147320
0x18000151d  mov     [rsp+1D8h+var_1A8], r13
0x180001522  mov     [rsp+1D8h+var_1B0], rax
0x180001527  mov     [rsp+1D8h+var_1B8], 4
0x180001530  call    EventingWriteEvent
0x180001535  jmp     loc_1800012C5
0x18000153a  cmp     dword ptr cs:xmmword_180169738, r12d
0x180001541  mov     dword ptr [rsp+1D8h+var_160], r12d
0x180001546  mov     [rsp+1D8h+var_168], eax
0x18000154a  jz      loc_1800012C5
0x180001550  mov     rdx, 4000000000000800h; unsigned __int64
0x18000155a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180001561  jz      loc_1800012C5
0x180001567  jmp     loc_180001474
0x18000156c  mov     [r14], esi
0x18000156f  jmp     loc_1800012C5
```
