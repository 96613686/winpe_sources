# CPrintTicketValidationFilter::HasValidNameSpaceOrNameAttributes(NCoreLibrary::TAutoPtrCOM<IXMLDOMNamedNodeMap> const &,long)

- ea: `0x18001e004`
- end: `0x18001e19d`
- name: `?HasValidNameSpaceOrNameAttributes@CPrintTicketValidationFilter@@IEAA_NAEBV?$TAutoPtrCOM@UIXMLDOMNamedNodeMap@@@NCoreLibrary@@J@Z`
- size: `409`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x18001e004`
- `0x180023010`

## string_xrefs

- `0x18001e0df`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c
bool __fastcall CPrintTicketValidationFilter::HasValidNameSpaceOrNameAttributes(__int64 a1, __int64 *a2, int a3)
{
  int v3; // ebx
  unsigned int v4; // edi
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  int v9; // edx
  int v10; // ecx
  unsigned __int16 *v11; // rax
  int v12; // edx
  int v13; // ecx
  char *v15; // [rsp+20h] [rbp-10h] BYREF
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-8h] BYREF
  __int64 v17; // [rsp+50h] [rbp+20h] BYREF
  char *v18; // [rsp+68h] [rbp+38h] BYREF

  v17 = a1;
  v3 = 0;
  v4 = 0;
  if ( a3 > 0 )
  {
    while ( v3 >= 0 )
    {
      v7 = *a2;
      v16 = 0;
      v17 = 0;
      v15 = 0;
      v18 = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 80LL))(v7, v4, &v16);
      if ( v3 >= 0 )
      {
        v3 = (**v16)(v16, &IID_IXMLDOMAttribute, &v17);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v17 + 328LL))(v17, &v15);
          if ( v3 >= 0 )
          {
            v3 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v17 + 312LL))(v17, &v18);
            if ( v3 >= 0 )
            {
              v8 = (unsigned __int16 *)v18;
              if ( !v18 )
                goto LABEL_11;
              do
              {
                v9 = *(unsigned __int16 *)((char *)v8 + (char *)L"http://www.w3.org/2000/xmlns/" - v18);
                v10 = *v8 - v9;
                if ( v10 )
                  break;
                ++v8;
              }
              while ( v9 );
              if ( v10 )
              {
LABEL_11:
                v11 = (unsigned __int16 *)v15;
                if ( !v15 )
                  goto LABEL_17;
                do
                {
                  v12 = *(unsigned __int16 *)((char *)v11 + (char *)L"name" - v15);
                  v13 = *v11 - v12;
                  if ( v13 )
                    break;
                  ++v11;
                }
                while ( v12 );
                if ( v13 )
                {
LABEL_17:
                  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v18);
                  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v15);
                  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
                  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
                  return 0;
                }
              }
            }
          }
        }
      }
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v18);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v15);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
      if ( (int)++v4 >= a3 )
        return v3 >= 0;
    }
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x18001e004  mov     [rsp-18h+arg_8], rbx
0x18001e009  mov     [rsp-18h+arg_10], rsi
0x18001e00e  mov     [rsp-18h+arg_0], rcx
0x18001e013  push    rbp
0x18001e014  push    rdi
0x18001e015  push    r14
0x18001e017  mov     rbp, rsp
0x18001e01a  sub     rsp, 30h
0x18001e01e  xor     ebx, ebx
0x18001e020  xor     edi, edi
0x18001e022  mov     esi, r8d
0x18001e025  mov     r14, rdx
0x18001e028  test    r8d, r8d
0x18001e02b  jle     loc_18001E15A
0x18001e031  test    ebx, ebx
0x18001e033  js      loc_18001E15A
0x18001e039  mov     rcx, [r14]
0x18001e03c  lea     r8, [rbp+var_8]
0x18001e040  mov     [rbp+var_8], 0
0x18001e048  mov     edx, edi
0x18001e04a  mov     [rbp+arg_0], 0
0x18001e052  mov     [rbp+var_10], 0
0x18001e05a  mov     [rbp+arg_18], 0
0x18001e062  mov     rax, [rcx]
0x18001e065  mov     rax, [rax+50h]
0x18001e069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e06e  mov     ebx, eax
0x18001e070  test    eax, eax
0x18001e072  js      loc_18001E12C
0x18001e078  mov     rcx, [rbp+var_8]
0x18001e07c  lea     r8, [rbp+arg_0]
0x18001e080  lea     rdx, IID_IXMLDOMAttribute
0x18001e087  mov     rax, [rcx]
0x18001e08a  mov     rax, [rax]
0x18001e08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e092  mov     ebx, eax
0x18001e094  test    eax, eax
0x18001e096  js      loc_18001E12C
0x18001e09c  mov     rcx, [rbp+arg_0]
0x18001e0a0  lea     rdx, [rbp+var_10]
0x18001e0a4  mov     rax, [rcx]
0x18001e0a7  mov     rax, [rax+148h]
0x18001e0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b3  mov     ebx, eax
0x18001e0b5  test    eax, eax
0x18001e0b7  js      short loc_18001E12C
0x18001e0b9  mov     rcx, [rbp+arg_0]
0x18001e0bd  lea     rdx, [rbp+arg_18]
0x18001e0c1  mov     rax, [rcx]
0x18001e0c4  mov     rax, [rax+138h]
0x18001e0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0d0  mov     ebx, eax
0x18001e0d2  test    eax, eax
0x18001e0d4  js      short loc_18001E12C
0x18001e0d6  mov     rax, [rbp+arg_18]
0x18001e0da  test    rax, rax
0x18001e0dd  jz      short loc_18001E101
0x18001e0df  lea     r8, aHttpWwwW3Org20_2; "http://www.w3.org/2000/xmlns/"
0x18001e0e6  sub     r8, rax
0x18001e0e9  movzx   ecx, word ptr [rax]
0x18001e0ec  movzx   edx, word ptr [rax+r8]
0x18001e0f1  sub     ecx, edx
0x18001e0f3  jnz     short loc_18001E0FD
0x18001e0f5  add     rax, 2
0x18001e0f9  test    edx, edx
0x18001e0fb  jnz     short loc_18001E0E9
0x18001e0fd  test    ecx, ecx
0x18001e0ff  jz      short loc_18001E12C
0x18001e101  mov     rax, [rbp+var_10]
0x18001e105  test    rax, rax
0x18001e108  jz      short loc_18001E175
0x18001e10a  lea     r8, aName; "name"
0x18001e111  sub     r8, rax
0x18001e114  movzx   ecx, word ptr [rax]
0x18001e117  movzx   edx, word ptr [rax+r8]
0x18001e11c  sub     ecx, edx
0x18001e11e  jnz     short loc_18001E128
0x18001e120  add     rax, 2
0x18001e124  test    edx, edx
0x18001e126  jnz     short loc_18001E114
0x18001e128  test    ecx, ecx
0x18001e12a  jnz     short loc_18001E175
0x18001e12c  lea     rcx, [rbp+arg_18]
0x18001e130  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001e135  lea     rcx, [rbp+var_10]
0x18001e139  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001e13e  lea     rcx, [rbp+arg_0]
0x18001e142  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e147  lea     rcx, [rbp+var_8]
0x18001e14b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e150  inc     edi
0x18001e152  cmp     edi, esi
0x18001e154  jl      loc_18001E031
0x18001e15a  shr     ebx, 1Fh
0x18001e15d  xor     bl, 1
0x18001e160  mov     al, bl
0x18001e162  mov     rbx, [rsp+30h+arg_8]
0x18001e167  mov     rsi, [rsp+30h+arg_10]
0x18001e16c  add     rsp, 30h
0x18001e170  pop     r14
0x18001e172  pop     rdi
0x18001e173  pop     rbp
0x18001e174  retn
0x18001e175  lea     rcx, [rbp+arg_18]
0x18001e179  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001e17e  lea     rcx, [rbp+var_10]
0x18001e182  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001e187  lea     rcx, [rbp+arg_0]
0x18001e18b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e190  lea     rcx, [rbp+var_8]
0x18001e194  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e199  xor     al, al
0x18001e19b  jmp     short loc_18001E162
```
