# Microsoft::Diagnostics::ScenariosSqliteTable::PrepareStatements(void)

- ea: `0x1802b2224`
- end: `0x1802b343d`
- name: `?PrepareStatements@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAXXZ`
- size: `4633`
- prototype: `void __fastcall(Microsoft::Diagnostics::ScenariosSqliteTable *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1802b1f50`

## callees

- `0x180024558`
- `0x180049bec`
- `0x18009c8c0`
- `0x18012bea8`
- `0x1801b2404`
- `0x1801b2c18`
- `0x18020aae4`
- `0x1802b078c`

## string_xrefs

- `0x1802b23ee`: `DELETE FROM Scenarios WHERE Hash = ?1`
- `0x1802b263e`: `DELETE FROM Triggers WHERE Hash = ?1`
- `0x1802b25dd`: `UPDATE Triggers SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b25a3`: `UPDATE Triggers SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b27eb`: `DELETE FROM Filters WHERE Hash = ?1`
- `0x1802b27b1`: `UPDATE Filters SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b2777`: `UPDATE Filters SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b290d`: `UPDATE Actions SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b2981`: `DELETE FROM Actions WHERE Hash = ?1`
- `0x1802b2947`: `UPDATE Actions SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b2b1e`: `UPDATE TraceProfiles SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b2ae4`: `UPDATE TraceProfiles SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b2c86`: `SELECT Type, BinaryRepresentation FROM Configurations WHERE Hash = ?1`
- `0x1802b2c38`: `INSERT INTO Configurations (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)`
- `0x1802b2bce`: `SELECT COUNT(1) FROM Configurations WHERE Hash = ?1`
- `0x1802b2b84`: `DELETE FROM TraceProfiles WHERE Hash = ?1`
- `0x1802b2d99`: `DELETE FROM Configurations WHERE Hash = ?1`
- `0x1802b2d34`: `UPDATE Configurations SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b2cfa`: `UPDATE Configurations SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b2cc0`: `SELECT RefCount FROM Configurations WHERE Hash = ?1`
- `0x1802b2fb3`: `DELETE FROM TelemetryEvents WHERE Hash = ?1`
- `0x1802b2f51`: `UPDATE TelemetryEvents SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b2f16`: `UPDATE TelemetryEvents SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b312d`: `UPDATE ScenarioStateModels SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b31c8`: `DELETE FROM ScenarioStateModels WHERE Hash = ?1`
- `0x1802b3167`: `UPDATE ScenarioStateModels SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b3371`: `UPDATE Transitions SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x1802b3337`: `UPDATE Transitions SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802b33d2`: `DELETE FROM Transitions WHERE Hash = ?1`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall Microsoft::Diagnostics::ScenariosSqliteTable::PrepareStatements(
        Microsoft::Diagnostics::ScenariosSqliteTable *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // r10
  _QWORD *v4; // rbx
  __int64 v5; // r10
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // r10
  __int64 v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // r10
  _QWORD *v13; // rbx
  __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rbx
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  _QWORD *v35; // rbx
  __int64 v36; // r10
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  _QWORD *v41; // rbx
  __int64 v42; // r10
  __int64 v43; // rax
  _QWORD *v44; // rbx
  __int64 v45; // r10
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rbx
  __int64 v51; // r10
  __int64 v52; // rax
  _QWORD *v53; // rbx
  __int64 v54; // r10
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  _QWORD *v59; // rbx
  __int64 v60; // r10
  __int64 v61; // rax
  _QWORD *v62; // rbx
  __int64 v63; // r10
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  _QWORD *v68; // rbx
  __int64 v69; // r10
  __int64 v70; // rax
  __int64 v71; // rax
  _QWORD *v72; // rbx
  __int64 v73; // r10
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  _QWORD *v77; // rbx
  __int64 v78; // r10
  _BYTE v79[16]; // [rsp+20h] [rbp-69h] BYREF
  const char *v80; // [rsp+30h] [rbp-59h] BYREF
  __int64 v81; // [rsp+38h] [rbp-51h]
  __int128 v82; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v83[8]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v84[8]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v85[8]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v86[8]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v87[8]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v88[8]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v89[8]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v90[8]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v91[80]; // [rsp+90h] [rbp+7h] BYREF
  void *v92; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v93; // [rsp+F8h] [rbp+6Fh] BYREF
  char v94; // [rsp+100h] [rbp+77h] BYREF
  char v95; // [rsp+108h] [rbp+7Fh] BYREF

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v91, (char *)this + 200);
  v2 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "SELECT COUNT(1) FROM Scenarios WHERE Hash = ?1";
  v81 = 46;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v3, v2, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 0;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v4 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "INSERT INTO Scenarios (Hash,NamespaceHash,BinaryRepresentation)VALUES (?1,?2,?3)";
  v81 = 80;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v5, v4, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 1;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v6 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
         &v93,
         *((_QWORD *)this + 5),
         "SELECT NamespaceHash FROM Scenarios WHERE Hash = ?1");
  LOWORD(v92) = 2;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v6);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v7 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
         &v93,
         *((_QWORD *)this + 5),
         "SELECT NamespaceHash, BinaryRepresentation FROM Scenarios WHERE Hash = ?1");
  LOWORD(v92) = 3;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v7);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v8 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM Scenarios WHERE Hash = ?1";
  v81 = 37;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v9, v8, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 4;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v10 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Triggers WHERE Hash = ?1");
  LOWORD(v92) = 5;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v10);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v11 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "INSERT INTO Triggers (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 82;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v12, v11, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 6;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v13 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "SELECT Type, BinaryRepresentation FROM Triggers WHERE Hash = ?1";
  v81 = 63;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v14, v13, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 7;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v15 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Triggers WHERE Hash = ?1");
  LOWORD(v92) = 8;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v15);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v16 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Triggers SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 9;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v16);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v17 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Triggers SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 10;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v17);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v18 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM Triggers WHERE Hash = ?1";
  v81 = 36;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v19, v18, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 11;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v20 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 12;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v20);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v21 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "INSERT INTO Filters (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)");
  LOWORD(v92) = 13;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v21);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v22 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 14;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v22);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v23 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 15;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v23);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v24 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Filters SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 16;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v24);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v25 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Filters SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 17;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v25);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v26 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "DELETE FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 18;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v26);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v27 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 19;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v27);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v28 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "INSERT INTO Actions (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)");
  LOWORD(v92) = 20;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v28);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v29 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 21;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v29);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v30 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 22;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v30);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v31 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Actions SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 23;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v31);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v32 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Actions SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 24;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v32);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v33 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "DELETE FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 25;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v33);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v34 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM TraceProfiles WHERE Hash = ?1");
  LOWORD(v92) = 40;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v34);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v35 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "INSERT INTO TraceProfiles (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 87;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v36, v35, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 41;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v37 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM TraceProfiles WHERE Hash = ?1");
  LOWORD(v92) = 42;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v37);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v38 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM TraceProfiles WHERE Hash = ?1");
  LOWORD(v92) = 43;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v38);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v39 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TraceProfiles SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 44;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v39);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v40 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TraceProfiles SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 45;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v40);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v41 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM TraceProfiles WHERE Hash = ?1";
  v81 = 41;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v42, v41, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 46;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v43 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Configurations WHERE Hash = ?1");
  LOWORD(v92) = 47;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v43);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v44 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "INSERT INTO Configurations (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 88;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v45, v44, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 48;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v46 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM Configurations WHERE Hash = ?1");
  LOWORD(v92) = 49;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v46);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v47 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Configurations WHERE Hash = ?1");
  LOWORD(v92) = 50;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v47);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v48 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Configurations SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 51;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v48);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v49 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Configurations SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 52;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v49);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v50 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM Configurations WHERE Hash = ?1";
  v81 = 42;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v51, v50, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 53;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v52 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM TelemetryEvents WHERE Hash = ?1");
  LOWORD(v92) = 54;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v52);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v53 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "INSERT INTO TelemetryEvents (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 89;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v54, v53, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 55;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v55 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM TelemetryEvents WHERE Hash = ?1");
  LOWORD(v92) = 56;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v55);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v56 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM TelemetryEvents WHERE Hash = ?1");
  LOWORD(v92) = 57;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v56);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v57 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TelemetryEvents SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 59;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v57);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v58 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TelemetryEvents SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 58;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v58);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v59 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM TelemetryEvents WHERE Hash = ?1";
  v81 = 43;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v60, v59, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 60;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v61 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v94,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM ScenarioStateModels WHERE Hash = ?1");
  LOWORD(v92) = 26;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v61);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v94);
  v62 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "INSERT INTO ScenarioStateModels (Hash,RefCount,BinaryRepresentation)VALUES (?1,?2,?3)";
  v81 = 85;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v63, v62, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 27;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v64 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v95,
          *((_QWORD *)this + 5),
          "SELECT BinaryRepresentation FROM ScenarioStateModels WHERE Hash = ?1");
  LOWORD(v92) = 28;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v64);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v95);
  v65 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v83,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM ScenarioStateModels WHERE Hash = ?1");
  LOWORD(v92) = 29;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v65);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v83);
  v66 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v84,
          *((_QWORD *)this + 5),
          "UPDATE ScenarioStateModels SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 30;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v66);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v84);
  v67 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v85,
          *((_QWORD *)this + 5),
          "UPDATE ScenarioStateModels SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 31;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v67);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v85);
  v68 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM ScenarioStateModels WHERE Hash = ?1";
  v81 = 47;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v69, v68, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 32;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v70 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v86,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Transitions WHERE Hash = ?1");
  LOWORD(v92) = 33;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v70);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v86);
  v71 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v87,
          *((_QWORD *)this + 5),
          "INSERT INTO Transitions (Hash,RefCount,BinaryRepresentation)VALUES (?1,?2,?3)");
  LOWORD(v92) = 34;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v71);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v87);
  v72 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "SELECT BinaryRepresentation FROM Transitions WHERE Hash = ?1";
  v81 = 60;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v73, v72, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 35;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v74 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v88,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Transitions WHERE Hash = ?1");
  LOWORD(v92) = 36;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v74);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v88);
  v75 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v89,
          *((_QWORD *)this + 5),
          "UPDATE Transitions SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 37;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v75);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v89);
  v76 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v90,
          *((_QWORD *)this + 5),
          "UPDATE Transitions SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 38;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v76);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v90);
  v77 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462860, v79);
  v80 = "DELETE FROM Transitions WHERE Hash = ?1";
  v81 = 39;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v78, v77, (__int64)&v80, (__int64)&v82);
  LOWORD(v92) = 39;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v91);
}

```

## disassembly

```asm
0x1802b2224  push    rbp
0x1802b2226  push    rbx
0x1802b2227  push    rsi
0x1802b2228  push    rdi
0x1802b2229  push    r12
0x1802b222b  push    r13
0x1802b222d  push    r14
0x1802b222f  push    r15
0x1802b2231  lea     rbp, [rsp-1Fh]
0x1802b2236  sub     rsp, 0A8h
0x1802b223d  mov     rdi, rcx
0x1802b2240  lea     rdx, [rcx+0C8h]
0x1802b2247  lea     rcx, [rbp+57h+var_50]
0x1802b224b  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1802b2250  nop
0x1802b2251  lea     rsi, [rdi+118h]
0x1802b2258  mov     rbx, [rdi+28h]
0x1802b225c  mov     r15d, 30h ; '0'
0x1802b2262  mov     ecx, r15d; Size
0x1802b2265  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802b226a  mov     r10, rax
0x1802b226d  mov     [rbp+57h+arg_0], rax
0x1802b2271  lea     rdx, [rbp+57h+var_C0]
0x1802b2275  lea     r14, qword_180462860
0x1802b227c  mov     rcx, r14
0x1802b227f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802b2284  movups  xmm0, xmmword ptr [rax]
0x1802b2287  movdqu  [rbp+57h+var_A0], xmm0
0x1802b228c  lea     rax, aSelectCount1Fr_3; "SELECT COUNT(1) FROM Scenarios WHERE Ha"...
0x1802b2293  mov     [rbp+57h+var_B0], rax
0x1802b2297  lea     r13d, [r15-2]
0x1802b229b  mov     [rbp+57h+var_A8], r13
0x1802b229f  lea     r9, [rbp+57h+var_A0]
0x1802b22a3  lea     r8, [rbp+57h+var_B0]
0x1802b22a7  mov     rdx, rbx
0x1802b22aa  mov     rcx, r10
0x1802b22ad  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802b22b2  nop
0x1802b22b3  mov     [rbp+57h+arg_8], rax
0x1802b22b7  xor     eax, eax
0x1802b22b9  mov     word ptr [rbp+57h+arg_0], ax
0x1802b22bd  lea     r9, [rbp+57h+arg_8]
0x1802b22c1  lea     r8, [rbp+57h+arg_0]
0x1802b22c5  lea     rdx, [rbp+57h+var_C0]
0x1802b22c9  mov     rcx, rsi
0x1802b22cc  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b22d1  nop
0x1802b22d2  lea     rcx, [rbp+57h+arg_8]
0x1802b22d6  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b22db  mov     rbx, [rdi+28h]
0x1802b22df  mov     ecx, r15d; Size
0x1802b22e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802b22e7  mov     r10, rax
0x1802b22ea  mov     [rbp+57h+arg_0], rax
0x1802b22ee  lea     rdx, [rbp+57h+var_C0]
0x1802b22f2  mov     rcx, r14
0x1802b22f5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802b22fa  movups  xmm0, xmmword ptr [rax]
0x1802b22fd  movdqu  [rbp+57h+var_A0], xmm0
0x1802b2302  lea     rax, aInsertIntoScen_0; "INSERT INTO Scenarios (Hash,NamespaceHa"...
0x1802b2309  mov     [rbp+57h+var_B0], rax
0x1802b230d  mov     [rbp+57h+var_A8], 50h ; 'P'
0x1802b2315  lea     r9, [rbp+57h+var_A0]
0x1802b2319  lea     r8, [rbp+57h+var_B0]
0x1802b231d  mov     rdx, rbx
0x1802b2320  mov     rcx, r10
0x1802b2323  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802b2328  nop
0x1802b2329  mov     [rbp+57h+arg_8], rax
0x1802b232d  lea     eax, [r15-2Fh]
0x1802b2331  mov     word ptr [rbp+57h+arg_0], ax
0x1802b2335  lea     r9, [rbp+57h+arg_8]
0x1802b2339  lea     r8, [rbp+57h+arg_0]
0x1802b233d  lea     rdx, [rbp+57h+var_C0]
0x1802b2341  mov     rcx, rsi
0x1802b2344  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b2349  nop
0x1802b234a  lea     rcx, [rbp+57h+arg_8]
0x1802b234e  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b2353  lea     r8, aSelectNamespac; "SELECT NamespaceHash FROM Scenarios WHE"...
0x1802b235a  mov     rdx, [rdi+28h]
0x1802b235e  lea     rcx, [rbp+57h+arg_8]
0x1802b2362  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b2367  nop
0x1802b2368  lea     ecx, [r15-2Eh]
0x1802b236c  mov     word ptr [rbp+57h+arg_0], cx
0x1802b2370  mov     r9, rax
0x1802b2373  lea     r8, [rbp+57h+arg_0]
0x1802b2377  lea     rdx, [rbp+57h+var_C0]
0x1802b237b  mov     rcx, rsi
0x1802b237e  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b2383  nop
0x1802b2384  lea     rcx, [rbp+57h+arg_8]
0x1802b2388  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b238d  lea     r8, aSelectNamespac_0; "SELECT NamespaceHash, BinaryRepresentat"...
0x1802b2394  mov     rdx, [rdi+28h]
0x1802b2398  lea     rcx, [rbp+57h+arg_8]
0x1802b239c  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b23a1  nop
0x1802b23a2  lea     ecx, [r15-2Dh]
0x1802b23a6  mov     word ptr [rbp+57h+arg_0], cx
0x1802b23aa  mov     r9, rax
0x1802b23ad  lea     r8, [rbp+57h+arg_0]
0x1802b23b1  lea     rdx, [rbp+57h+var_C0]
0x1802b23b5  mov     rcx, rsi
0x1802b23b8  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b23bd  nop
0x1802b23be  lea     rcx, [rbp+57h+arg_8]
0x1802b23c2  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b23c7  mov     rbx, [rdi+28h]
0x1802b23cb  mov     ecx, r15d; Size
0x1802b23ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802b23d3  mov     r10, rax
0x1802b23d6  mov     [rbp+57h+arg_0], rax
0x1802b23da  lea     rdx, [rbp+57h+var_C0]
0x1802b23de  mov     rcx, r14
0x1802b23e1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802b23e6  movups  xmm0, xmmword ptr [rax]
0x1802b23e9  movdqu  [rbp+57h+var_A0], xmm0
0x1802b23ee  lea     rax, aDeleteFromScen_0; "DELETE FROM Scenarios WHERE Hash = ?1"
0x1802b23f5  mov     [rbp+57h+var_B0], rax
0x1802b23f9  mov     [rbp+57h+var_A8], 25h ; '%'
0x1802b2401  lea     r9, [rbp+57h+var_A0]
0x1802b2405  lea     r8, [rbp+57h+var_B0]
0x1802b2409  mov     rdx, rbx
0x1802b240c  mov     rcx, r10
0x1802b240f  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802b2414  nop
0x1802b2415  mov     [rbp+57h+arg_8], rax
0x1802b2419  lea     eax, [r15-2Ch]
0x1802b241d  mov     word ptr [rbp+57h+arg_0], ax
0x1802b2421  lea     r9, [rbp+57h+arg_8]
0x1802b2425  lea     r8, [rbp+57h+arg_0]
0x1802b2429  lea     rdx, [rbp+57h+var_C0]
0x1802b242d  mov     rcx, rsi
0x1802b2430  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b2435  nop
0x1802b2436  lea     rcx, [rbp+57h+arg_8]
0x1802b243a  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b243f  lea     r8, aSelectCount1Fr_1; "SELECT COUNT(1) FROM Triggers WHERE Has"...
0x1802b2446  mov     rdx, [rdi+28h]
0x1802b244a  lea     rcx, [rbp+57h+arg_8]
0x1802b244e  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b2453  nop
0x1802b2454  lea     ecx, [r15-2Bh]
0x1802b2458  mov     word ptr [rbp+57h+arg_0], cx
0x1802b245c  mov     r9, rax
0x1802b245f  lea     r8, [rbp+57h+arg_0]
0x1802b2463  lea     rdx, [rbp+57h+var_C0]
0x1802b2467  mov     rcx, rsi
0x1802b246a  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b246f  nop
0x1802b2470  lea     rcx, [rbp+57h+arg_8]
0x1802b2474  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b2479  mov     rbx, [rdi+28h]
0x1802b247d  mov     ecx, r15d; Size
0x1802b2480  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802b2485  mov     r10, rax
0x1802b2488  mov     [rbp+57h+arg_0], rax
0x1802b248c  lea     rdx, [rbp+57h+var_C0]
0x1802b2490  mov     rcx, r14
0x1802b2493  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802b2498  movups  xmm0, xmmword ptr [rax]
0x1802b249b  movdqu  [rbp+57h+var_A0], xmm0
0x1802b24a0  lea     rax, aInsertIntoTrig; "INSERT INTO Triggers (Hash,Type,RefCoun"...
0x1802b24a7  mov     [rbp+57h+var_B0], rax
0x1802b24ab  mov     [rbp+57h+var_A8], 52h ; 'R'
0x1802b24b3  lea     r9, [rbp+57h+var_A0]
0x1802b24b7  lea     r8, [rbp+57h+var_B0]
0x1802b24bb  mov     rdx, rbx
0x1802b24be  mov     rcx, r10
0x1802b24c1  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802b24c6  nop
0x1802b24c7  mov     [rbp+57h+arg_8], rax
0x1802b24cb  lea     eax, [r15-2Ah]
0x1802b24cf  mov     word ptr [rbp+57h+arg_0], ax
0x1802b24d3  lea     r9, [rbp+57h+arg_8]
0x1802b24d7  lea     r8, [rbp+57h+arg_0]
0x1802b24db  lea     rdx, [rbp+57h+var_C0]
0x1802b24df  mov     rcx, rsi
0x1802b24e2  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b24e7  nop
0x1802b24e8  lea     rcx, [rbp+57h+arg_8]
0x1802b24ec  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b24f1  mov     rbx, [rdi+28h]
0x1802b24f5  mov     ecx, r15d; Size
0x1802b24f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802b24fd  mov     r10, rax
0x1802b2500  mov     [rbp+57h+arg_0], rax
0x1802b2504  lea     rdx, [rbp+57h+var_C0]
0x1802b2508  mov     rcx, r14
0x1802b250b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802b2510  movups  xmm0, xmmword ptr [rax]
0x1802b2513  movdqu  [rbp+57h+var_A0], xmm0
0x1802b2518  lea     rax, aSelectTypeBina_0; "SELECT Type, BinaryRepresentation FROM "...
0x1802b251f  mov     [rbp+57h+var_B0], rax
0x1802b2523  mov     [rbp+57h+var_A8], 3Fh ; '?'
0x1802b252b  lea     r9, [rbp+57h+var_A0]
0x1802b252f  lea     r8, [rbp+57h+var_B0]
0x1802b2533  mov     rdx, rbx
0x1802b2536  mov     rcx, r10
0x1802b2539  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802b253e  nop
0x1802b253f  mov     [rbp+57h+arg_8], rax
0x1802b2543  lea     eax, [r15-29h]
0x1802b2547  mov     word ptr [rbp+57h+arg_0], ax
0x1802b254b  lea     r9, [rbp+57h+arg_8]
0x1802b254f  lea     r8, [rbp+57h+arg_0]
0x1802b2553  lea     rdx, [rbp+57h+var_C0]
0x1802b2557  mov     rcx, rsi
0x1802b255a  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b255f  nop
0x1802b2560  lea     rcx, [rbp+57h+arg_8]
0x1802b2564  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b2569  lea     r8, aSelectRefcount_6; "SELECT RefCount FROM Triggers WHERE Has"...
0x1802b2570  mov     rdx, [rdi+28h]
0x1802b2574  lea     rcx, [rbp+57h+arg_8]
0x1802b2578  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b257d  nop
0x1802b257e  lea     ecx, [r15-28h]
0x1802b2582  mov     word ptr [rbp+57h+arg_0], cx
0x1802b2586  mov     r9, rax
0x1802b2589  lea     r8, [rbp+57h+arg_0]
0x1802b258d  lea     rdx, [rbp+57h+var_C0]
0x1802b2591  mov     rcx, rsi
0x1802b2594  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b2599  nop
0x1802b259a  lea     rcx, [rbp+57h+arg_8]
0x1802b259e  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b25a3  lea     r8, aUpdateTriggers; "UPDATE Triggers SET RefCount = RefCount"...
0x1802b25aa  mov     rdx, [rdi+28h]
0x1802b25ae  lea     rcx, [rbp+57h+arg_8]
0x1802b25b2  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b25b7  nop
0x1802b25b8  lea     ecx, [r15-27h]
0x1802b25bc  mov     word ptr [rbp+57h+arg_0], cx
0x1802b25c0  mov     r9, rax
0x1802b25c3  lea     r8, [rbp+57h+arg_0]
0x1802b25c7  lea     rdx, [rbp+57h+var_C0]
0x1802b25cb  mov     rcx, rsi
0x1802b25ce  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b25d3  nop
0x1802b25d4  lea     rcx, [rbp+57h+arg_8]
0x1802b25d8  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b25dd  lea     r8, aUpdateTriggers_0; "UPDATE Triggers SET RefCount = RefCount"...
0x1802b25e4  mov     rdx, [rdi+28h]
0x1802b25e8  lea     rcx, [rbp+57h+arg_8]
0x1802b25ec  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b25f1  nop
0x1802b25f2  lea     ecx, [r15-26h]
0x1802b25f6  mov     word ptr [rbp+57h+arg_0], cx
0x1802b25fa  mov     r9, rax
0x1802b25fd  lea     r8, [rbp+57h+arg_0]
0x1802b2601  lea     rdx, [rbp+57h+var_C0]
0x1802b2605  mov     rcx, rsi
0x1802b2608  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b260d  nop
0x1802b260e  lea     rcx, [rbp+57h+arg_8]
0x1802b2612  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b2617  mov     rbx, [rdi+28h]
0x1802b261b  mov     ecx, r15d; Size
0x1802b261e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802b2623  mov     r10, rax
0x1802b2626  mov     [rbp+57h+arg_0], rax
0x1802b262a  lea     rdx, [rbp+57h+var_C0]
0x1802b262e  mov     rcx, r14
0x1802b2631  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802b2636  movups  xmm0, xmmword ptr [rax]
0x1802b2639  movdqu  [rbp+57h+var_A0], xmm0
0x1802b263e  lea     rax, aDeleteFromTrig; "DELETE FROM Triggers WHERE Hash = ?1"
0x1802b2645  mov     [rbp+57h+var_B0], rax
0x1802b2649  mov     [rbp+57h+var_A8], 24h ; '$'
0x1802b2651  lea     r9, [rbp+57h+var_A0]
0x1802b2655  lea     r8, [rbp+57h+var_B0]
0x1802b2659  mov     rdx, rbx
0x1802b265c  mov     rcx, r10
0x1802b265f  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802b2664  nop
0x1802b2665  mov     [rbp+57h+arg_8], rax
0x1802b2669  lea     eax, [r15-25h]
0x1802b266d  mov     word ptr [rbp+57h+arg_0], ax
0x1802b2671  lea     r9, [rbp+57h+arg_8]
0x1802b2675  lea     r8, [rbp+57h+arg_0]
0x1802b2679  lea     rdx, [rbp+57h+var_C0]
0x1802b267d  mov     rcx, rsi
0x1802b2680  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x1802b2685  nop
0x1802b2686  lea     rcx, [rbp+57h+arg_8]
0x1802b268a  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x1802b268f  lea     r8, aSelectCount1Fr_5; "SELECT COUNT(1) FROM Filters WHERE Hash"...
0x1802b2696  mov     rdx, [rdi+28h]
0x1802b269a  lea     rcx, [rbp+57h+arg_8]
0x1802b269e  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x1802b26a3  nop
0x1802b26a4  lea     ecx, [r15-24h]
0x1802b26a8  mov     word ptr [rbp+57h+arg_0], cx
0x1802b26ac  mov     r9, rax
0x1802b26af  lea     r8, [rbp+57h+arg_0]
0x1802b26b3  lea     rdx, [rbp+57h+var_C0]
0x1802b26b7  mov     rcx, rsi
  ... truncated ...
```
