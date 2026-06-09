# LoadUnmanagedCOMObject

- ea: `0x18000a6a4`
- end: `0x18000a87c`
- name: `LoadUnmanagedCOMObject`
- size: `472`
- prototype: `__int64 __fastcall(struct _GUID *, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d134`

## callees

- `0x180003070`
- `0x18000663c`
- `0x180008710`
- `0x180009af4`
- `0x18000a6a4`
- `0x18000a884`
- `0x180029774`
- `0x180029b38`
- `0x18002e680`

## pseudocode

```c
__int64 __fastcall LoadUnmanagedCOMObject(struct _GUID *a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  _QWORD *v9; // rax
  unsigned int ServerUsingCLSID; // eax
  CLRFullPath *v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned __int16 ***v14; // rax
  bool v15; // sf
  char v16; // al
  CLRFullPath *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v23[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+80h] [rbp-80h]
  __int128 v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+B8h] [rbp-48h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  int v31; // [rsp+C8h] [rbp-38h]
  __int64 v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  __int64 v34; // [rsp+E0h] [rbp-20h]
  int v35; // [rsp+E8h] [rbp-18h]
  __int64 v36; // [rsp+F0h] [rbp-10h]

  v19 = 0;
  v20 = 0;
  v9 = (_QWORD *)BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::operator&(
                   &v19,
                   &v18);
  ServerUsingCLSID = FindServerUsingCLSID(a1, *v9);
  v11 = v18;
  v12 = 1;
  v13 = ServerUsingCLSID >> 31;
  if ( *(_QWORD *)v18 )
    *((_DWORD *)v18 + 2) = 1;
  if ( !(_BYTE)v13 )
  {
    if ( !CLRFullPath::GetFullPath(v11) || (int)LoadUnmanagedCOMObjectVersioned(v19, 0, (_DWORD)a1, a2, a3, a4, a5) < 0 )
    {
      v26 = 0;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      v25 = 0;
      v27 = 1;
      v28 = 1;
      v29 = 0;
      v30 = 0;
      v31 = 1;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = -1;
      if ( (int)RuntimeRequest::ComputeVersionString(v23, 0) < 0
        || (int)LoadUnmanagedCOMObjectVersioned(v19, v23[0], (_DWORD)a1, a2, a3, a4, a5) < 0 )
      {
        v21 = 0;
        v22 = 0;
        v14 = (unsigned __int16 ***)BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::operator&(
                                      &v21,
                                      &v18);
        if ( (int)FindVersionForCLSID(a1, *v14) < 0
          || (v15 = (int)LoadUnmanagedCOMObjectVersioned(v19, v21, (_DWORD)a1, a2, a3, a4, a5) < 0, v16 = 1, v15) )
        {
          v16 = 0;
        }
        if ( *(_QWORD *)v18 )
          *((_DWORD *)v18 + 2) = 1;
        if ( !v16 )
        {
          Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v21);
          RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v23);
          v12 = -2146232575;
          goto LABEL_18;
        }
        Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v21);
      }
      RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v23);
    }
    v12 = 0;
  }
LABEL_18:
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v19);
  return v12;
}

```

## disassembly

```asm
0x18000a6a4  push    rbp
0x18000a6a6  push    rbx
0x18000a6a7  push    rsi
0x18000a6a8  push    rdi
0x18000a6a9  push    r12
0x18000a6ab  push    r13
0x18000a6ad  push    r14
0x18000a6af  push    r15
0x18000a6b1  lea     rbp, [rsp-8]
0x18000a6b6  sub     rsp, 108h
0x18000a6bd  mov     r12, rdx
0x18000a6c0  mov     rdi, rcx
0x18000a6c3  xor     r13d, r13d
0x18000a6c6  lea     rdx, [rsp+140h+var_100]
0x18000a6cb  lea     rcx, [rsp+140h+var_F8]
0x18000a6d0  mov     [rsp+140h+var_F8], r13
0x18000a6d5  mov     [rsp+140h+var_F0], r13d
0x18000a6da  mov     r14, r9
0x18000a6dd  mov     r15, r8
0x18000a6e0  call    ??I?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::operator&(void)
0x18000a6e5  mov     rcx, rdi
0x18000a6e8  mov     rdx, [rax]
0x18000a6eb  call    FindServerUsingCLSID
0x18000a6f0  mov     rcx, [rsp+140h+var_100]; this
0x18000a6f5  lea     ebx, [r13+1]
0x18000a6f9  shr     eax, 1Fh
0x18000a6fc  cmp     [rcx], r13
0x18000a6ff  jz      short loc_18000A704
0x18000a701  mov     [rcx+8], ebx
0x18000a704  test    al, al
0x18000a706  jnz     loc_18000A85C
0x18000a70c  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18000a711  mov     rsi, [rbp+40h+arg_20]
0x18000a715  test    rax, rax
0x18000a718  jz      short loc_18000A747
0x18000a71a  mov     rcx, [rsp+140h+var_F8]
0x18000a71f  mov     r9, r12
0x18000a722  mov     [rsp+140h+var_110], rsi
0x18000a727  mov     r8, rdi
0x18000a72a  mov     [rsp+140h+var_118], r14
0x18000a72f  xor     edx, edx
0x18000a731  mov     [rsp+140h+var_120], r15
0x18000a736  call    LoadUnmanagedCOMObjectVersioned
0x18000a73b  test    eax, eax
0x18000a73d  js      short loc_18000A747
0x18000a73f  mov     ebx, r13d
0x18000a742  jmp     loc_18000A85C
0x18000a747  xorps   xmm0, xmm0
0x18000a74a  mov     [rbp+40h+var_A0], r13
0x18000a74e  xorps   xmm1, xmm1
0x18000a751  movdqa  xmmword ptr [rsp+140h+var_D0], xmm0
0x18000a757  xor     edx, edx; int
0x18000a759  movdqa  [rbp+40h+var_C0], xmm1
0x18000a75e  lea     rcx, [rsp+140h+var_D0]; this
0x18000a763  movdqa  [rbp+40h+var_B0], xmm0
0x18000a768  mov     [rbp+40h+var_98], rbx
0x18000a76c  mov     [rbp+40h+var_90], rbx
0x18000a770  mov     [rbp+40h+var_88], r13d
0x18000a774  mov     [rbp+40h+var_80], r13
0x18000a778  mov     [rbp+40h+var_78], ebx
0x18000a77b  mov     [rbp+40h+var_70], r13
0x18000a77f  mov     [rbp+40h+var_68], r13
0x18000a783  mov     [rbp+40h+var_60], r13
0x18000a787  mov     [rbp+40h+var_58], r13d
0x18000a78b  mov     [rbp+40h+var_50], 0FFFFFFFFFFFFFFFFh
0x18000a793  call    ?ComputeVersionString@RuntimeRequest@@QEAAJH@Z; RuntimeRequest::ComputeVersionString(int)
0x18000a798  test    eax, eax
0x18000a79a  js      short loc_18000A7D3
0x18000a79c  mov     rdx, [rsp+140h+var_D0]
0x18000a7a1  mov     r9, r12
0x18000a7a4  mov     rcx, [rsp+140h+var_F8]
0x18000a7a9  mov     r8, rdi
0x18000a7ac  mov     [rsp+140h+var_110], rsi
0x18000a7b1  mov     [rsp+140h+var_118], r14
0x18000a7b6  mov     [rsp+140h+var_120], r15
0x18000a7bb  call    LoadUnmanagedCOMObjectVersioned
0x18000a7c0  test    eax, eax
0x18000a7c2  js      short loc_18000A7D3
0x18000a7c4  lea     rcx, [rsp+140h+var_D0]; this
0x18000a7c9  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18000a7ce  jmp     loc_18000A73F
0x18000a7d3  lea     rdx, [rsp+140h+var_100]
0x18000a7d8  mov     [rsp+140h+var_E8], r13
0x18000a7dd  lea     rcx, [rsp+140h+var_E8]
0x18000a7e2  mov     [rsp+140h+var_E0], r13d
0x18000a7e7  call    ??I?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::operator&(void)
0x18000a7ec  mov     rcx, rdi; struct _GUID *
0x18000a7ef  mov     rdx, [rax]; unsigned __int16 **
0x18000a7f2  call    ?FindVersionForCLSID@@YAJAEBU_GUID@@PEAPEAG@Z; FindVersionForCLSID(_GUID const &,ushort * *)
0x18000a7f7  test    eax, eax
0x18000a7f9  js      short loc_18000A825
0x18000a7fb  mov     rdx, [rsp+140h+var_E8]
0x18000a800  mov     r9, r12
0x18000a803  mov     rcx, [rsp+140h+var_F8]
0x18000a808  mov     r8, rdi
0x18000a80b  mov     [rsp+140h+var_110], rsi
0x18000a810  mov     [rsp+140h+var_118], r14
0x18000a815  mov     [rsp+140h+var_120], r15
0x18000a81a  call    LoadUnmanagedCOMObjectVersioned
0x18000a81f  test    eax, eax
0x18000a821  mov     al, bl
0x18000a823  jns     short loc_18000A828
0x18000a825  mov     al, r13b
0x18000a828  mov     rcx, [rsp+140h+var_100]
0x18000a82d  cmp     [rcx], r13
0x18000a830  jz      short loc_18000A835
0x18000a832  mov     [rcx+8], ebx
0x18000a835  lea     rcx, [rsp+140h+var_E8]
0x18000a83a  test    al, al
0x18000a83c  jz      short loc_18000A848
0x18000a83e  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000a843  jmp     loc_18000A7C4
0x18000a848  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000a84d  lea     rcx, [rsp+140h+var_D0]; this
0x18000a852  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18000a857  mov     ebx, 80131701h
0x18000a85c  lea     rcx, [rsp+140h+var_F8]
0x18000a861  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000a866  mov     eax, ebx
0x18000a868  add     rsp, 108h
0x18000a86f  pop     r15
0x18000a871  pop     r14
0x18000a873  pop     r13
0x18000a875  pop     r12
0x18000a877  pop     rdi
0x18000a878  pop     rsi
0x18000a879  pop     rbx
0x18000a87a  pop     rbp
0x18000a87b  retn
```
